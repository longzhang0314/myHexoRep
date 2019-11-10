---
title: Java中截取字符串问题
date: 2019-10-19 14:37:52
tags:
---

```
stringObj.split([separator，[limit]]) 
```

1. 直接截取：

```
String s = "a,b,c,d,,,";
String[] strArr = s.split(",");
//此时strArr为a,b,c,d
```

1. 带limit条件截取

```
String s = "a,b,c,d,,,";
String[] strArr = s.split(","，-1);
//此时strArr为a,b,c,d,"","",""
```

3.截取特殊字符时需要使用转义字符

```
String s = "a$b$c";
String[] strArr = s.split("\\$");
//此时strArr为a,b,c
```