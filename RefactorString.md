#问题
给定A,B两个字符串，串中的字符全都是小写英文字母（即a -> z）。判断能否只使用A串中的字符拼出B串，A串中的每个字符只准使用一次。
>例如：
>A = "aaab"    B = "aaa"     true
>A = "aabb"    B= "aaa"      false
>A = "aaab"    B = "abaa"   true
>A = "aaab"    B = "aaac"   false

函数原型：
bool canConstruct(const char* A, const char* B)
{

}

#思路
使用一个数组来记录a中每个字母出现的次数，再比较b中每个字母出现的次数，如果后者大，则false
优化：遍历a的时候，对应元素加1，遍历b的时候，对应元素减1，如果出现负数，则返回false

#代码
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