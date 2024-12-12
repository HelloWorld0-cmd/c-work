## 实验四 循环结构程序设计
### 一，实验目的
1、熟悉用 while 语句，do-while 语句和 for 语句实现循环的方法。
2、掌握在程序设计中用循环的方法实现各种算法（如穷举、迭代、递推等）。 3、掌握 continue 语句和break 语句的使用。
4、熟练掌握循环结构的嵌套。
5、练习调试与修改程序。

### 二、实验准备
1、复习 while、do-while 和 for 语句的特点和适用条件。
2、复习 break 和 continue 的区别。

### 三、实验内容
以下程序是用来计算S=1+2+3+4+...+10，请更正以下程序的错误，并上机调试。 1、
```c++
#include<stdio.h> void main()
{
    int i=1; while(i<10) 
    sum+=i;
    ++i;
    printf(“sum=%d\n”,sum);
}
```
> 答，循环条件改为i<=10,int i和printf中间的两行加大括号

2、
```c++
#include <stdio.h> 
void main()
{
    int i=sum=0; do{
    sum+=i;
    ++i;
    }while (i<10)
    printf("sum=%d\n",sum);
}
```
> 初始化时改为`int i = 0,sum = 0;`

3、
```c++
#include <stdio.h> void main()
 
{
int i=sum=0; do{
sum+=i;
++i;
}while(i<10)
printf ("sum=%d\n" ,sum);
}
```
> 同(2),修改初始化的写法

4、输入并运行下面的程序，观察程序的运行结果。 
```c++
#include <stdio.h>
void main()
{
    int n;
    while (1)
    {
        printf("'Enter a number:"); scanf ("%d" ‚n);
        if (n%2==1)
        {
            printf("I said"); 
            continue;
        }
        break;
    }
    printf("Thanks. I needed that！");
}
```
> 程序旨在找到一个偶数，若是奇数则输出`I said`并重新输入，若是偶数则输出`Thanks.I need that!`并结束程序
