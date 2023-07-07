# C-p41-2-
C语言学习笔记 p41 指针笔试面试题讲解(2)
#include<stdio.h>
int main()
{
    //二维数组
    int a[3][4]={0};
    printf("%d\n"sizeof(a));//48
    printf("%d\n"sizeof(a[0][0]));//4
    printf("%d\n"sizeof(a[0]));//16 a[0]相当于第一行作为一维数组的数组名，sizeof(arr[0])把数组名单独放在sizeof()内，计算的是第一行的大小
    printf("%d\n"sizeof(a[0]+1));//4 a[0]是第一行的数组名，数组名此时是首元素的地址，a[0]其实就是第一行第一个元素的地址，所以a[0]+1就是第一行第二个元素的地址-地址就是4/8个字节
    printf("%d\n"sizeof(*(a[0]+1)));//4 *(a[0]+1))是第一行第二个元素，大小是4个字节
    printf("%d\n"sizeof(a+1));//4 a是二维数组的数组名，没有sizeof(数组名)，也没有&(数组名)，所以a是首元素地址，而二维数组的首元素是第一行，(a+1)就是第二行
    printf("%d\n"sizeof(*(a+1)));//16 计算第二行的大小，单位是字节
    printf("%d\n"sizeof(&a[0]+1));//4 第二行的地址
    printf("%d\n"sizeof(*(&a[0]+1)));//16
    printf("%d\n"sizeof(*a));//16 a是首元素地址-第一行的地址，*a就是第一行，sizeof(*a)就是计算第一行的大小
    printf("%d\n"sizeof(a[3]));//16 sizeof括号内的表达式不参与计算，所以不算非法访问
    return 0;
    }

    int main()
    {
        int a[5]={1,2,3,4,5};
        int *ptr=(*int)(&a+1);
        printf("%d,%d",*(a+1),*(pre-1));
        return 0;
    }//输出为2,5


    struct Test
    {
        int Num;
        char* pcName;
        short sDate;
        char cha[2];
        short sBa[4];
    }*p;
    int main()
    {
        printf("%p\n",p+0x1);
        printf("%p\n",(unsigned long)p+0x1);
        printf("%p\n",(unsigned int*)p+0x1);
        return 0;
    }
