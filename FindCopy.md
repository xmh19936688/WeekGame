#����
n������������������˳�����һ�������У�������һ�����ظ��ģ��������ķ����ҳ�������֡�

#˼·
n��������������ֵΪ`(��Сֵ+���ֵ)*n/2`�����n������һ���ظ��ģ���ͨ����Сֵ�����ֵ���㳤��Ϊ`n-1`ʱ�ĺͣ���ԭ��������Ϊ�ظ�ֵ��
��һ��ѭ���У��ҵ���Сֵ�����ֵ�������������ۺϡ�

#����
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
	//�ҳ���Сֵ�����ֵ����
	int min=num[0],max=num[0],sum=0;
	for(int i=0;i<length;i++){
		sum+=num[i];
		if(num[i]<min){
			min=num[i];
		}else if(num[i]>max){
			max=num[i];
		}
	}
	//�ҵ��������ε�ֵ
	int value=(int)(sum-(min+max)/2.0*(length-1));
	return value;
}
```