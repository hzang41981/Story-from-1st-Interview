# KMP
[Reference 1](https://github.com/hzang41981/leetcode-master/blob/master/problems/0028.%E5%AE%9E%E7%8E%B0strStr.md)

前缀表：记录下标 i 以及之前的字符串中，有多大长度的相同前缀后缀；
前缀：所有以第一个字符开始，不包含最后一个字符的子串；
后缀：所有以最后一个结尾，不包含第一个字符的子串；
最长相等前后缀：'aaa' => 2, 'aaaa' => 3
前缀表：
Example：‘aabaabaabf’ 查找 ‘aabaaf’
```
下标5之前这部分的字符串（也就是字符串aabaa）的最长相等的前缀 和 后缀字符串是 子字符串aa ，因为找到了最长相等的前缀和后缀，匹配失败的位置是后缀子串的后面，那么我们找到与其相同的前缀的后面从新匹配就可以了。
```
