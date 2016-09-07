#问题
计算x的n次方

函数原型：`double myPow( double x, int n ){}`

#思路
1. 将n二进制化，按位计算。最低位为1时，累乘x；次低位为1时，累乘x的平方；以此类推。
1. 兼容性：根据x与0的大小关系和n与0的大小关系可以分为多种情况，需要在代码中处理
1. 代码优化：让算法兼容各种情况，适当减少if
1. 异常处理：当`x=0`且`n<0`时，会出现`1/0`的情况，对此异常不错处理。因为该方法设计认为x为合法参数，如果出现异常应在主调函数中处理。

#代码
```
#include <stdio.h>

double pow(double x,int n)
{
    double r =1;
    if(n<0)
    {
        x=1/x;
        n=-n;
    }
    
    for(int m=1;m!=0;m<<=1,x*=x)
    {
        if(m&n){
            r*=x;
        }
    }
    
    return r;
}

int main()
{
    printf("%f\n",pow(2,0));
    return 0;
}
```