# 数据结构

## 基本概念与术语

**数据**是对客观事物的符号表示，在计算机科学中是指能输入到计算机并能由计算机程序进行处理的符号的总称。

数据的最小单位是**数据项**（数据项不可再分割），若干数据项组成一个**数据元素**，数据元素是数据的基本单位。性质相同的数据元素的集合即为**数据对象**。

**数据结构**（data structure）是相互之间存在的一种或多种特定关系的数据元素的集合。

科学家沃思认为，数据结构 + 算法 = 程序

结构：
集合——除了同属一个集合，相互之间没有任何其他关系；
线性——元素间存在一对一的关系；
树形——元素间存在一对多的关系；
网状——元素间存在多对多的关系；

数据结构由四部分组成：数据对象、数据的逻辑结构、数据的存储结构和数据的操作运算。

## 抽象数据类型（abstract data type）

抽象数据类型（ADT），指基于一个逻辑类型的数据类型以及这个类型上的一组操作。

ADT=<D,S,P> ，其中，D代表数据对象，S代表D上的关系集，P代表对D的基本操作集。
