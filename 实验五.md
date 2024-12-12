## 实验五 数组

### 一、实验目的
1、掌握一维数组和二维数组的定义、赋值和输入输出的方法。
2、掌握字符数组和字符串函数的使用。
3、掌握与数组有关的算法（特别是排序算法）。
### 二、实验准备
1、复习数组的基本知识。
2、复习字符串数组的特点和常用的字符串处理函数。
### 三、实验内容
编写下列问题的源程序并上机调试运行。
1、用选择法对 10 个整数排序(10 个整数用 scanf 函数输入)。
源码如下：
```c++
#include<stdio.h>
int main()
{
    int arr[10];
    for(int i = 0;i<=9;i++)
    scanf("%d",arr+i);
    int t;
    for(int i = 0;i<=9;i++)
    {
        for(int j  = 0;j<=i;j++)
        {
            if(arr[j]>arr[i])
            {
                t = arr[i];
                arr[i] = arr[j];
                arr[j] = t;
            }
        }
    }
    for(int i = 0;i<=9;i++)
    printf("%d ",*(arr+i));
    return 0;
}
```

2、有 15 个数存放在一个数组中，输入一个数，要求用折半查找法找出该数是数组中第几个元素的值。如果该数不在数组中，则输出“无此数”。15 个数用赋初值的方法在程序中给出。要找的数用scanf 函数输入。
源码如下:
```c++
#include<stdio.h>
int main()
{
    int arr[16];
    for(int i = 1;i<=15;i++)
    scanf("%d",arr+i);
    int num;scanf("%d",&num);
    int l = 0,r = 16;
    while(l+1<r)
    {
        int mid1 = (r-l)>>1;
        int mid2 = (r+l)>>1;
        for(int i = 1;i<=mid1;i++)
        if(arr[l+i]==num)
        {
            printf("%d",l+i);
            return 0;
        }
        l = mid2;
    }
    printf("无此数");
    return 0;
}
```
3、将两个字符串连接起来，不要用 strcat 函数。
```c++
#include<stdio.h>
#include<string.h>
int main()
{
    char str1[40];
    char str2[20];
    scanf("%s",str1);
    scanf("%s",str2);
    int l1 = strlen(str1),l2 = strlen(str2);
    for(int i = l1;i<=l1+l2;i++)
    {
        str1[i] = str2[i-l1];
    }
    printf("%s",str1);
    return 0;
}
```
4、找出一个二维数组的“鞍点”，即该位置上的元素在该行上最大，在该列上最小。也可能没有鞍点。此二维数组可以设定如下，其中，数组元素的值用赋初值方法在程序中指定。 
9    80 205 40
90  -60  96  1
210  -3 101 89
```c++
#include<stdio.h>
#include<string.h>
int arr[201][201];
// 对每行每列的极值做标记
int h[201];
int l[201];
int main()
{
    int n,m;scanf("%d %d",&n,&m);
    for(int i = 1;i<=n;i++)
    l[i] = 1e9;
    for(int i = 1;i<=n;i++)
        for(int j = 1;j<=m;j++)
            {
                scanf("%d",&arr[i][j]);
                if(arr[i][j]>h[i]) h[i] = arr[i][j];
                if(arr[i][j]<l[j]) l[j] = arr[i][j];
            }
    // for(int i = 1;i<=n;i++)
    // {
    //     printf("%d ",h[i]);
    // }
    // printf("\n");
    // for(int i = 1;i<=m;i++)
    // {
    //     printf("%d ",l[i]);
    // }
    for(int i = 1;i<=n;i++)
        for(int j = 1;j<=m;j++)
        {
            if(arr[i][j]==h[i]&&arr[i][j]==l[j])
            {
                printf("%d\n",arr[i][j]);
            }
        }
    return 0;
}
```
