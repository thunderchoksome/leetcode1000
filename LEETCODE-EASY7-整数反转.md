#LEETCODE-EASY7-整数反转
---
给出一个 32 位的有符号整数，你需要将这个整数中每位上的数字进行反转。

示例 1:

输入: 123
输出: 321
 示例 2:

输入: -123
输出: -321
示例 3:

输入: 120
输出: 21

注意:
假设我们的环境只能存储得下 32 位的有符号整数，则其数值范围为 [−231,  231 − 1]。请根据这个假设，如果反转后整数溢出那么就返回 0。

---
##myCode
```

	class Solution:
    	def reverse(self, x: int) -> int:
        	c = []
        	if x >= 0:
            	flag = 1
            	while flag == 1:
                	d = int(x / 10)
                	b = int(x % 10)
                	c.append(b)
                	b = d
                	if b == 0:
                	    flag = 0
                	else:
                	    x = d
            	sums = str()
            	for i in c:
                	sums += str(i)
            	sums = int(sums)
        	elif x < 0:
            	x = -x
            	flag = 1
            	while flag == 1:
            	        d = int(x / 10)
            	        b = int(x % 10)
            	        c.append(b)
            	        b = d
            	        if b == 0:
            	            flag = 0
            	        else:
            	            x = d
            	sums = '-'
            	for i in c:
            	    sums += str(i)
            	sums = int(sums)
        	if -2**31 <= sums <= 2**31-1:
            	return sums
        	else:
            	return 0
```

###执行用时 :36 ms
###内存消耗 :13.7 MB
##力扣上其他大佬str的灵活运用

###执行用时 :40 ms   内存消耗 :13.8 MB

```

	class Solution:
    	def reverse(self, x):
    	    """
    	    :type x: int
    	    :rtype: int
    	    """
	
    	    if x >= 2**31-1 or x <= -2**31: return 0
    	    else:
    	        strg = str(x)
    	        if x >= 0 :
    	            revst = strg[::-1]
    	        else:
    	            temp = strg[1:] 
    	            temp2 = temp[::-1] 
    	            revst = "-" + temp2
    	        if int(revst) >= 2**31-1 or int(revst) <= -2**31: return 0
            	else: return int(revst)
```
