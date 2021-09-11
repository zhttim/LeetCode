## 剑指 Offer 05. 替换空格

https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/

## 题目描述

```
请实现一个函数，把字符串 s 中的每个空格替换成"%20"。

 

示例 1：

输入：s = "We are happy."
输出："We%20are%20happy."

```


## 代码

Java :
```Java

public static String replaceSpace(StringBuffer str) {
        if (str == null) {
            return null;
        }
		//选用 StringBuilder 单线程使用，比较快，选不选都行
        StringBuilder sb = new StringBuilder();
		//使用 sb 逐个复制 str ，碰到空格则替换，否则直接复制
        for (int i = 0; i < str.length(); i++) {
		//str.charAt(i) 为 char 类型，为了比较需要将其转为和 " " 相同的字符串类型
            if (" ".equals(String.valueOf(str.charAt(i)))){
                sb.append("%20");
            } else {
                sb.append(str.charAt(i));
            }
        }
        return sb.toString();
    }

```
