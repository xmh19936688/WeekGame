#问题
一位单身人士混入了一个只允许情侣参加的聚会，已知每对情侣身上都贴了相同的号码，并且不同情侣的号码互不相同，单身人士身上的号码也是唯一的，找到他/她。
C函数原型：返回只出现一次的号码
int FindSignle( int* numbers, int n )
{
    
}
>例如：对输入a[1,1,2,9,2,3,3,4,6,6,5,7,5,9,7,8,8]，返回4

#思路
特点：相同的两个数做异或运算，结果为0。将整个数组异或到一起，成对的将会相互作用为0，剩下的就是单独出现的。

#代码
```
#include<stdio.h>
#include<stdlib.h>

int findSingle(int * num,int length);

void main(){
	int num[]={1,1,2,9,2,3,3,4,6,6,5,7,5,9,7,8,8};
	int result=findSingle(num,sizeof(num)/sizeof(num[0]));
	printf("%d\n",result);
}

int findSingle(int * num,int length){
    int value=0;
    for(int i=0;i<length;i++){
        value^=num[i];
    }
    return value;
}
```
