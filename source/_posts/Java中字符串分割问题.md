---
title: Java中字符串分割问题
date: 2019-10-19 14:37:52
tags:
---

```
stringObj.split([separator，[limit]]) 
```

1. 直接分割：

```
String s = "a,b,c,d,,,";
String[] strArr = s.split(",");
//此时strArr为a,b,c,d
```

2. 带limit条件分割:

```
String s = "a,b,c,d,,,";
String[] strArr = s.split(","，-1);
//此时strArr为a,b,c,d,"","",""
```

3. 分割特殊字符时需要使用转义字符:

```
String s = "a$b$c";
String[] strArr = s.split("\\$");
//此时strArr为a,b,c
```

