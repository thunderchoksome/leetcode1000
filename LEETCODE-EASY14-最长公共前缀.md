#LEETCODE-EASY14-最长公共前缀
---
编写一个函数来查找字符串数组中的最长公共前缀。

如果不存在公共前缀，返回空字符串 ""。

示例 1:

输入: ["flower","flow","flight"]
输出: "fl"
示例 2:

输入: ["dog","racecar","car"]
输出: ""
解释: 输入不存在公共前缀。

---
##今天是失败的一天，没有成功，在参考了一位大佬的解答下才完成
```

	char * longestCommonPrefix(char ** strs, int strsSize)	{
    	if (strsSize == 0) {
    	    return "";
    	}
    	if (strsSize == 1) return strs[0];
    	int i = 0, j, sign = 1;
    	char test;
    	for (; sign; ++i) {
    	   test = strs[0][i];
    	    for (j = 0; j  < strsSize; ++j) 
    	        if ((!strs[j][i]) || (strs[j][i] != test)) 
    	            {   sign = 0;     break;  }
    	}
    	strs[0][i-1] = '\0';
    	return strs[0];
	}	
```
继续加油！