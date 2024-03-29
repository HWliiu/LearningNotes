- [TODO](#todo)
- [第 18 章 探讨 C++ 新标准](#第-18-章-探讨-c-新标准)
  - [复习前面介绍过的 C++11 功能](#复习前面介绍过的-c11-功能)
    - [新类型：](#新类型)
    - [统一的初始化：](#统一的初始化)
    - [声明](#声明)
    - [智能指针](#智能指针)
    - [异常规范方面的修改](#异常规范方面的修改)
    - [作用域内枚举](#作用域内枚举)
    - [对类的修改](#对类的修改)
    - [模板和 STL 方面的修改](#模板和-stl-方面的修改)
    - [右值引用](#右值引用)
  - [移动语义和右值引用](#移动语义和右值引用)
    - [为何需要移动语义](#为何需要移动语义)
    - [一个移动示例](#一个移动示例)
    - [移动构造函数解析](#移动构造函数解析)
    - [赋值](#赋值)
    - [强制移动](#强制移动)
  - [新的类功能](#新的类功能)
    - [特殊的成员函数](#特殊的成员函数)
    - [默认的方法和禁用的方法](#默认的方法和禁用的方法)
    - [委托构造函数](#委托构造函数)
    - [继承构造函数](#继承构造函数)
    - [管理虚方法：override 和 final](#管理虚方法override-和-final)
  - [Lambda 函数](#lambda-函数)
    - [比较函数针、函数符和 Lambda 函数](#比较函数针函数符和-lambda-函数)
    - [为何使用 lambda](#为何使用-lambda)
  - [包装器](#包装器)
    - [包装器 function 及模板的低效性](#包装器-function-及模板的低效性)
    - [修复问题](#修复问题)
  - [可变参数模板](#可变参数模板)
    - [模板和函数参数包](#模板和函数参数包)
    - [展开参数包](#展开参数包)
    - [在可变参数模板函数中使用递归](#在可变参数模板函数中使用递归)
  - [C++11 新增的其他功能](#c11-新增的其他功能)
    - [并行编程](#并行编程)
    - [新增的库](#新增的库)

---

### TODO

---

### 第 18 章 探讨 C++ 新标准

#### 复习前面介绍过的 C++11 功能

##### 新类型：

![](assets/2023-04-23-10-53-22.png)

##### 统一的初始化：

![](assets/2023-04-23-10-57-39.png)
![](assets/2023-04-23-10-58-07.png)

##### 声明

（注：有`int x;` 则`(x)`的类型为 `int &`）
![](assets/2023-04-23-11-27-22.png)
![](assets/2023-04-23-17-55-49.png)

##### 智能指针

![](assets/2023-04-23-17-56-27.png)

##### 异常规范方面的修改

![](assets/2023-04-23-17-58-08.png)
![](assets/2023-04-23-17-58-23.png)

##### 作用域内枚举

![](assets/2023-04-23-17-59-11.png)

##### 对类的修改

![](assets/2023-04-23-18-01-06.png)
![](assets/2023-04-23-18-06-44.png)

##### 模板和 STL 方面的修改

![](assets/2023-04-23-18-57-14.png)
![](assets/2023-04-23-18-58-40.png)

##### 右值引用

![](assets/2023-04-23-19-05-27.png)
![](assets/2023-04-23-19-05-42.png)

#### 移动语义和右值引用

##### 为何需要移动语义

![](assets/2023-04-23-20-25-14.png)
![](assets/2023-04-23-20-25-34.png)

##### 一个移动示例

![](assets/2023-04-23-20-49-44.png)
![](assets/2023-04-23-20-50-30.png)
![](assets/2023-04-23-20-51-22.png)
![](assets/2023-04-23-20-51-47.png)

##### 移动构造函数解析

![](assets/2023-04-23-20-57-13.png)
![](assets/2023-04-23-20-57-27.png)

##### 赋值

![](assets/2023-04-23-20-59-00.png)

##### 强制移动

![](assets/2023-04-23-21-03-07.png)
![](assets/2023-04-23-21-11-45.png)
![](assets/2023-04-23-21-18-34.png)
![](assets/2023-04-23-21-20-05.png)
![](assets/2023-04-23-21-23-00.png)

#### 新的类功能

##### 特殊的成员函数

![](assets/2023-04-23-21-50-45.png)
![](assets/2023-04-23-21-52-55.png)

##### 默认的方法和禁用的方法

![](assets/2023-04-23-21-56-55.png)
![](assets/2023-04-23-22-01-24.png)

##### 委托构造函数

![](assets/2023-04-23-22-03-18.png)

##### 继承构造函数

![](assets/2023-04-23-22-09-03.png)
![](assets/2023-04-23-22-09-21.png)
![](assets/2023-04-23-22-14-32.png)

##### 管理虚方法：override 和 final

![](assets/2023-04-23-22-15-34.png)

#### Lambda 函数

##### 比较函数针、函数符和 Lambda 函数

![](assets/2023-04-23-22-28-24.png)
![](assets/2023-04-23-22-44-23.png)

##### 为何使用 lambda

![](assets/2023-04-23-22-52-01.png)

#### 包装器

![](assets/2023-04-23-23-00-58.png)
![](assets/2023-04-23-23-01-19.png)

##### 包装器 function 及模板的低效性

![](assets/2023-04-23-23-27-04.png)
![](assets/2023-04-23-23-30-02.png)
![](assets/2023-04-23-23-31-09.png)

##### 修复问题

![](assets/2023-04-23-23-32-51.png)

#### 可变参数模板

![](assets/2023-04-23-23-37-08.png)

##### 模板和函数参数包

![](assets/2023-04-23-23-41-06.png)
![](assets/2023-04-23-23-41-21.png)

##### 展开参数包

![](assets/2023-04-23-23-43-38.png)

##### 在可变参数模板函数中使用递归

![](assets/2023-04-23-23-45-54.png)
![](assets/2023-04-23-23-46-07.png)

#### C++11 新增的其他功能

##### 并行编程

![](assets/2023-04-23-23-48-42.png)

##### 新增的库

![](assets/2023-04-23-23-49-41.png)
![](assets/2023-04-23-23-49-57.png)
