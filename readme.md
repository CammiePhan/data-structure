# 数据结构

[基本概念与术语](#基本概念与术语)  
[抽象数据类型](#抽象数据类型)  
[算法与算法分析](#算法与算法分析)  


## 基本概念与术语

**数据**是对客观事物的符号表示，在计算机科学中是指能输入到计算机并能由计算机程序进行处理的符号的总称。

数据的最小单位是**数据项**（数据项不可再分割），若干数据项组成一个**数据元素**，数据元素是数据的基本单位。性质相同的数据元素的集合即为**数据对象**。

**数据结构**（data structure）是相互之间存在的一种或多种特定关系的数据元素的集合。

科学家沃思认为，数据结构 + 算法 = 程序

结构：  
- 集合  除了同属一个集合，相互之间没有任何其他关系；
- 线性  元素间存在一对一的关系；
- 树形  元素间存在一对多的关系；
- 网状  元素间存在多对多的关系；

![结构](photo/1.png)

数据结构由四部分组成：数据对象、数据的逻辑结构、数据的存储结构和数据的操作运算。

## 抽象数据类型

抽象数据类型（abstract data type），ADT，指基于一个逻辑类型的数据类型以及这个类型上的一组操作。

· ADT=<D,S,P> · ，其中，D代表数据对象，S代表D上的关系集，P代表对D的基本操作集。
格式： 
```
//以下为伪码，不是写在程序中的
ADT Name{
	数据对象: <对数据的定义>
	数据关系集: <数据关系的定义>
	基本操作集: <基本操作的定义>
}ADT Name

```

其中，基本操作的格式，如下  
	基本操作名 (参数表)
	初始条件: <初始条件的描述>
	操作结果: <操作结果的描述>
*引用参数以&开头*

例，定义复数抽象数据类型：
```
//伪码
ADT Complex{
	D={e1,e2|e1,e2 ∈ realset} 					//数据对象
	S={<e1,e2>|e1表示实数部分，e2表示虚数部分} 	//数据关系
	
	AssignComplex(&a,e1,e2)
	操作结果:构造复数a，e1,e2分别被赋予实部和虚部的值

	DestroyComplex(&a)
	操作结果：销毁复数a

	GetComplex(a,&e1)
	初始条件：复数已经存在
	操作结果：得到实部的值

	GetComplex(a,&e2)
	初始条件：复数已经存在
	操作结果：得到虚部

	AddComplex(a,b,&sum)
	初始条件：复数a,b存在
	操作结果：得到两个复数a,b的和

}ADT Complex

```
该抽象数据类型的实现：  

```c
typedef struct{
	float realpart;
	float imagpart;
}complex;				//定义结构体类型

void Assign(complex &z, float realval, float imagval);	//调用自定义函数，构造一个复数

void add(complex z1, complex z2, complex &sum);		//调用自定义函数，计算两个复数之和

void getreal(complex z);	//调用自定义函数，得到实部的值

//自定义函数

void add(complex z1, complex z2, complex &sum){
	sum.realpart = z1.realpart + z2.realpart;
	sum.imagpart = z1.imagpart + z2.imagpart;
}
//其他的自定义函数，暂且省略

```

## 算法与算法分析

沃思：数据结构 + 算法 = 程序

算法，即解决问题的一种方法或过程，是计算机操作步骤的集合。  
*算法与程序* 的区别：程序是必须按照某种程序设计语言的语法编写的，可以在计算机上直接运行的；而算法可以用文字表示、流程图、伪码来描述，供人们阅读、交流的。

一个算法应该具有：正确性、具体性、确定性、有限性、可终止性

算法分析，即估算一个算法的效率。

### 时间复杂度

算法的运行时间，设每条语句执行一次所需时间为单位时间，则一个算法的运行时间就是该算法中所有语句的频度之和。

 T(n)=O(f(n))

几种常见的时间复杂度

- O(1):常数时间
- O(log2n)：对数时间
- O(n)：线性时间
- O(nlog2n)：线性对数时间
- O(n2):平方时间
- O(n3):立方时间
- O(2^n):指数时间

上述的时间复杂度的优劣次序如下（n>=16):
O(1)<O(log2n)<O(n)<O(nlog2n)<O(n2)<O(n3)<O(2^n)


### 空间复杂度

算法的存储空间大小

空间复杂度的度量，表示随着问题规模（用n表示）的增大，算法运行所需存储空间的增长速度。

S(n) = O(d(n))