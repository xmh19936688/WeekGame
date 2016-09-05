#问题
n个连续的整数被打乱顺序放在一个数组中，其中有一个是重复的，请用最快的方法找出这个数字。

#思路
n连续的整数，其值为`(最小值+最大值)*n/2`。如果n个中有一个重复的，则通过最小值与最大值计算长度为`n-1`时的和，与原数组和做差即为重复值。
在一次循环中，找到最小值、最大值，并计算数组综合。

#代码
```
#include<stdio.h>
#include<stdlib.h>

int find(int * num,int length);

void main(){
	int num[]={1,8,2,4,9,6,5,2,3,7};
	int result=find(num,sizeof(num)/sizeof(num[0]));
	printf("value:%d\n",result);
}

int find(int * num,int length){
	//找出最小值、最大值、和
	int min=num[0],max=num[0],sum=0;
	for(int i=0;i<length;i++){
		sum+=num[i];
		if(num[i]<min){
			min=num[i];
		}else if(num[i]>max){
			max=num[i];
		}
	}
	//找到出现两次的值
	int value=(int)(sum-(min+max)/2.0*(length-1));
	return value;
}
```