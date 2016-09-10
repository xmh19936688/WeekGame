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

函数原型：`double myPow( double x, int n ){}`
