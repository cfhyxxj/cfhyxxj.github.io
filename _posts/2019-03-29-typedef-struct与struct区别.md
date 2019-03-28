---
layout:     post
title:      typedef struct与struct区别
subtitle:   
date:       2019-03-29
author:     春风化雨
header-img: img/tqb.jpg
catalog: true
tags:
    - c		
    - c++
---

## typedef

`typedef struct`一般用于c语言

如：

```c
typdef struct Student{
	int num；
}Stu;
```

`Stu`表示结构体类型，`Stu=Struct Stduent`

即   可这样声明 `Stu stu1;`

​	也可这样声明 `Struct Student stu1;`

```c
typdef struct{
	int num；
}Stu;
```

只能用`Stu stu1；`

```c
typdef struct Student{
	int num；
};
```

只能用`Struct Student stu1;`



只有struct多用于c++

```c
struct Student{
	int num；
}stu1;
```

`stu1`是一个变量

