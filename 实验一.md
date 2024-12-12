# 实验一 数据类型、运算符与表达式

## 一、实验目的

1. 了解算法的概念、特性、算法在程序设计中的地位。
2. 熟悉算法的表示方法。
3. 掌握用流程图表示一个算法。
4. 能独立设计一个问题的算法,并根据该算法编出问题的程序。
5. 掌握 C 语言数据类型，熟悉如何定义一个整型、字符型和实型变量，以及对它们赋值的方法，了解以上类型数据输出时所用的格式转换符。
6. 学会使用 C 的有关算术运算符，以及包含这些运算符的表达式，特别是自加、自减运算符的使用。
7. 进一步熟悉 C 程序的编辑、编译、连接和运行的过程。

## 二、实验准备

1. 复习算法的概念和特性。
2. 复习算法的几种表示方式。
3. 复习 C 语言的数据类型。
4. 复习各种运算符和表达式。

## 三、实验内容

### 1、运行程序并回答问题：

```
#include<stdio.h>
int main()
{
    printf("%c", '／007');
    return 0;
}
```
![Image](http://i0.hdslb.com/bfs/new_dyn/4c186d7a1a9cf4a2627b5bb43404a40a3546738243668772.png)


> 问题:如果执行 printf("%c'＂,0x7)会得到什么结果?为什么?

![Image](http://i0.hdslb.com/bfs/new_dyn/c917f3f7b20c83b2f4f1f0eca7aad37b3546738243668772.png)

答：执行printf("%c'＂,0x7)代码后，没有见到可见的字符。

因为无论是0x7，还是\007,他们所表示的ASCII码字符为DEL，这是一个不可见的字符。

```c++
#include<stdio.h> 
void main() 
{
    char c1,c2; 
    c1=getchar(); 
    c2=ge tchar(); 
    putchar(c1) ; 
    putchar(c2); 
}
```


> 问题：把c1，c2定义成整型变量是否可以？为什么？采用同样的输入值观察结果。 

运行结果如下:
![p](http://i0.hdslb.com/bfs/new_dyn/a78eac3cdf3b4adf6cfaf9812b66448e3546738243668772.png)
![p](http://i0.hdslb.com/bfs/new_dyn/31f301bfd15e0c195d827e197d3e78133546738243668772.png)

答案:可以，若换成整型变量，在getchar时会存入字符的ascii码值，在putchar时再将ascii码值转换为字符，故两种方式是等效的。

----
### 2、输入程序并运行: 
```C++
#include<stdio .h> 
void main() 
{ 
    char c1,c2; 
    c1=97;c2=98; 
    printf("％c %c" ,c1,c2); 
}
```
在此基础上: 
·加printf("%d,%d",c1,c2)；运行。 
·将第二行改为:int c1,c2；运行。 
·将第三行改为:c1=300;c2=400;运行

#### 三次操作的运行结果依次为:

---

![](http://i0.hdslb.com/bfs/new_dyn/7ee56794e3f3b5c165494fb5c50697563546738243668772.png)

---
![2](http://i0.hdslb.com/bfs/new_dyn/da5bdc4de98531b6cb9dddbda4f849c73546738243668772.png)

---
![3](http://i0.hdslb.com/bfs/new_dyn/3ed822eeb7503ebd0d2517d36c4254663546738243668772.png)

---
### 3、输入程序并运行：
```c++ 
#include<stdio .h> 
void main() 
{
    char c1='a',c2='b',c3='c',c4='\101' ,c5='\116'; 
    printf("a%cb%c\tc%c\tabc\n" ,c1,c2,c3); 
    printf("\t\b%c%c",c4,c5); 
}
```
程序运行结果如下:
![](http://i0.hdslb.com/bfs/new_dyn/7e6794d2b11de3b33891eb69a3d6bb793546738243668772.png)

