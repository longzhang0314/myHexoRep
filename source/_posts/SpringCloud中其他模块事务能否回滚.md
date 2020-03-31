---
title: "SpringCloud中其他模块事务能否回滚"
date: 2019-09-09T11:20:30+08:00
draft: true
---

在处理业务逻辑时，遇到异常回滚数据库操作是非常常见的，但是，在SpringCloud的项目中，如果遇到业务抛异常需要回滚调用的其他模块数据库操作，能否有效呢？<br>
**1. 使用@Transactional注解在方法上**
<br>
发现无法回滚，可以回滚本地自己模块的操作，但无法回滚调用的其他模块的数据库操作。
<br>
**2. 使用手动事务**
<br>
手动设置回滚点在需要回滚的操作之前，抛异常后手动回滚事务。<br>

```
//设置回滚点
Object savePoint = TransactionAspectSupport.currentTransactionStatus().createSavepoint(); 
//数据库代码
/*
    代码~~~
*/
//手动回滚
TransactionAspectSupport.currentTransactionStatus().rollbackToSavepoint(savePoint);
```
根据最终结果发现，这种方式也是无效的。
<br><br>
#### 结论
SpringCloud模块中，每个模块对于自己模块的事务管理都是独立的，调用其他模块的服务，想要在本地通过回滚的方式回滚数据库操作是不现实的，所以，需要在代码设计之初就要考虑到这种情况，根据某些确定的条件之后再去做数据库操作，如果确实需要根据结果做回滚操作，可以再将数据update回去或者delete掉。也可以采用分布式事务框架。