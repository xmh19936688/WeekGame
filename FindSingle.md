#����
һλ������ʿ������һ��ֻ�������²μӵľۻᣬ��֪ÿ���������϶�������ͬ�ĺ��룬���Ҳ�ͬ���µĺ��뻥����ͬ��������ʿ���ϵĺ���Ҳ��Ψһ�ģ��ҵ���/����
C����ԭ�ͣ�����ֻ����һ�εĺ���
int FindSignle( int* numbers, int n )
{
    
}
>���磺������a[1,1,2,9,2,3,3,4,6,6,5,7,5,9,7,8,8]������4

#˼·
�ص㣺��ͬ����������������㣬���Ϊ0���������������һ�𣬳ɶԵĽ����໥����Ϊ0��ʣ�µľ��ǵ������ֵġ�

#����
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
