#问题
一个一维数组，其元素是非负整数，代表从这一位置可向前移动的最大步数
一开始，你位于数组的第一个元素上，判断自己是否能到达最后一个元素。
>例如：
>[2, 3, 0, 1, 4] 可以到达
>[3, 2, 1, 0, 4] 不能到达

#思路
一步一步向前走，实时对比当前能到达的最远处于数组长度

#代码
```
#include<stdio.h>
#include<stdlib.h>

int canReash(int * num,int length);
int true=1,false=-1;

void main(){
	int num[]={2, 3, 0, 1, 4};
	int result=canReash(num,sizeof(num)/sizeof(num[0]));
	if(result==true){
	    printf("success\n");
	}else if(result==false){
	    printf("fail\n");
	}
}

int canReash(int * num,int length){
    int max=num[0];
    int index=0;
	do{
	    index++;
	    max--;
	    if(max<num[index]){
	        max=num[index];
	    }
	    if(max==0){
	        break;
	    }
	}while(index<length);
	if(index>=length-1){
	    return true;
	}else{
	    return false;
	}
}
```