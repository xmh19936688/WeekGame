#����
����A,B�����ַ��������е��ַ�ȫ����СдӢ����ĸ����a -> z�����ж��ܷ�ֻʹ��A���е��ַ�ƴ��B����A���е�ÿ���ַ�ֻ׼ʹ��һ�Ρ�
>���磺
>A = "aaab"    B = "aaa"     true
>A = "aabb"    B= "aaa"      false
>A = "aaab"    B = "abaa"   true
>A = "aaab"    B = "aaac"   false

����ԭ�ͣ�
bool canConstruct(const char* A, const char* B)
{

}

#˼·
ʹ��һ����������¼a��ÿ����ĸ���ֵĴ������ٱȽ�b��ÿ����ĸ���ֵĴ�����������ߴ���false
�Ż�������a��ʱ�򣬶�ӦԪ�ؼ�1������b��ʱ�򣬶�ӦԪ�ؼ�1��������ָ������򷵻�false

#����
```
#include<stdio.h>
#include<string.h>

int check(const char * a,const char *b);
int true=1,false=-1;

void main(){
	int result=check("aaabb","abb");
	printf("%d\n",result);
}

int check(const char * a,const char *b){
    int count[26]={};
    int length=strlen(a);
    for(int i=0;i<length;i++){
        count[a[i]-'a']++;
    }
    length=strlen(b);
    for(int i=0;i<length;i++){
        int index=b[i]-'a';
        count[index]--;
        if(count[index]<0){
            return false;
        }
    }
    return true;
}
```