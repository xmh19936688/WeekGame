#����
һ��һά���飬��Ԫ���ǷǸ��������������һλ�ÿ���ǰ�ƶ��������
һ��ʼ����λ������ĵ�һ��Ԫ���ϣ��ж��Լ��Ƿ��ܵ������һ��Ԫ�ء�
>���磺
>[2, 3, 0, 1, 4] ���Ե���
>[3, 2, 1, 0, 4] ���ܵ���

#˼·
һ��һ����ǰ�ߣ�ʵʱ�Աȵ�ǰ�ܵ������Զ�������鳤��

#����
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