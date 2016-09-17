#问题
子序列

两个字符串a，b，判断a是否是b的子序列。子序列是指a中的每个字符在b中都存在，且a中任意两个字符的先后顺序与它们在b中的先后顺序完全相同，但b中的某些字符可以不在a中出现。

>如：
```
a = "abc"    b = "aabbcc"    true
a = "aabcc"  b = "aabbcc"  true
a = "acb"   b = “aabbcc”    false
a = "abd"   b = “aabbcc”    false
```

函数原型：`bool isSubsequence(const char* a, const char* b) {}`

#思路
 这个比较简单，不说了

#代码
```
//go
package main

import "fmt"

func main() {
   result:=isSubsequence("abc","abbcc")
   fmt.Printf("%t\n",result)
}

func isSubsequence(a string,b string)(bool){
    al:=len(a)
    bl:=len(b)
    i:=0
    j:=0
    for i<al && j<bl {
        if a[i]==b[j] {
            i++
            j++
        }else{
            j++
        }
    }
    return i==al;
}
```
