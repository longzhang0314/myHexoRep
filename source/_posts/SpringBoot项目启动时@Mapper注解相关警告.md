---
title: "SpringBoot项目启动时@Mapper注解相关警告"
date: 2019-09-09T11:26:59+08:00
draft: true
categories:
- Spring
---

```
2019-08-27 15:27:27 | WARN  | main | org.mybatis.spring.mapper.ClassPathMapperScanner | Skipping MapperFactoryBean with name 'Xxx1Mapper' and 'com.demo.finance.mapper.Xxx1Mapper' mapperInterface. Bean already defined with the same name!
2019-08-27 15:27:27 | WARN  | main | org.mybatis.spring.mapper.ClassPathMapperScanner | Skipping MapperFactoryBean with name 'YyMapper' and 'com.demo.finance.mapper.YyMapper' mapperInterface. Bean already defined with the same name!
2019-08-27 15:27:27 | WARN  | main | org.mybatis.spring.mapper.ClassPathMapperScanner | Skipping MapperFactoryBean with name 'ZzMapper' and 'com.demo.finance.mapper.ZzMapper' mapperInterface. Bean already defined with the same name!
2019-08-27 15:27:27 | WARN  | main | org.mybatis.spring.mapper.ClassPathMapperScanner | Skipping MapperFactoryBean with name 'AaMapper' and 'com.demo.finance.mapper.AaMapper' mapperInterface. Bean already defined with the same name!
2019-08-27 15:27:27 | WARN  | main | org.mybatis.spring.mapper.ClassPathMapperScanner | Skipping MapperFactoryBean with name 'BbMapper' and 'com.demo.finance.mapper.BbMapper' mapperInterface. Bean already defined with the same name!
2019-08-27 15:27:27 | WARN  | main | org.mybatis.spring.mapper.ClassPathMapperScanner | Skipping MapperFactoryBean with name 'CcMapper' and 'com.demo.finance.mapper.CcMapper' mapperInterface. Bean already defined with the same name!
```
项目启动时，控制台打印上述日志，原因是在Dao层使用了@Mapper注解，同时在启动类上添加了@MapperScane注解。
#### 解决方案
1. 只使用@Mapper注解，无需在启动类上开启扫描；
2. Dao层使用@Repository注解，并在启动类上使用@MapperScane("mapper目录")进行扫描