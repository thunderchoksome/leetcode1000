#LEETCODE-EASY9-回文数
---
判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。

示例 1:

输入: 121

输出: true

示例 2:

输入: -121

输出: false

解释: 从左向右读, 为 -121 。 从右向左读, 为 121- 。因此它不是一个回文数。

示例 3:

输入: 10

输出: false

解释: 从右向左读, 为 01 。因此它不是一个回文数。

进阶:

你能不将整数转为字符串来解决这个问题吗？

---
##我能！然后。。。
```



	bool isPalindrome(int x){
    	int i=0,turnx=0,sign=0;
    	if(x<0)
    	   return false;
    	else
    	{
    	    sign=x;
    	    while(sign!=0)
    	    {
    	        sign=sign/10;
    	        i++;
    	    }
    	    sign=x;
    	    while(i!=0)
    	    {
    	        turnx=turnx+(x%10)*pow(10,(i-1));
    	        x=x/10;
    	        i--;   
    	    }
    	    if(turnx==sign)
    	        return true;
    	    else
    	        return false;
    	}
	}	
```

执行用时 :
36 ms
, 在所有 C 提交中击败了
7.04%
的用户

内存消耗 :
7.2 MB
, 在所有 C 提交中击败了
80.41%
的用户    

---
##执行用时为 0 ms 的范例
---
```

	bool isPalindrome(int x){
    	
    	if(x<0)return false;
    	
    	int tmpx = x;
    	
    	long r = x%10;
    	x /= 10;
    	
    	if(r==0 && x>0) return false;
    	
    	while(x!=0){
    	    r = r*10 + x%10;
    	    x /= 10;
    	}
    	
    	if(r != tmpx)return false;
    		return true;
		}
```

差距在于x逆转的处理和他还把结尾为0的去了大大缩小了处理的范围，这个算法优点在于一次循环就解决了数的逆转，而我的还要傻傻的去数这个数是多少位的再用循环去实现逆转。
好好吸收！继续加油努力！