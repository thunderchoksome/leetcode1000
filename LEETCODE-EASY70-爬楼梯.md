#LEETCODE-EASY70-爬楼梯
---
假设你正在爬楼梯。需要 n 阶你才能到达楼顶。

每次你可以爬 1 或 2 个台阶。你有多少种不同的方法可以爬到楼顶呢？

注意：给定 n 是一个正整数。


示例 1：


输入： 2

输出： 2

解释： 有两种方法可以爬到楼顶。

1.  1 阶 + 1 阶

2.  2 阶

示例 2：


输入： 3

输出： 3

解释： 有三种方法可以爬到楼顶。

1.  1 阶 + 1 阶 + 1 阶
  
2.  1 阶 + 2 阶

3.  2 阶 + 1 阶

---
```

	int climbStairs(int n){
    
    	return count1(0,n);
    
	}
	int count1(int i,int n)
	{
   	if(i>n)
       	return 0;
   	if(i==n)
    	   return 1;
   	return count1(i+1,n)+count1(i+2,n);
        
        
	}
```

斐波那契数列的应用，我的做法是暴力法。虽然能达到目的，但是在时间空间上都有很大的浪费。
大佬的（java版）


```

		public class Solution {
    		public int climbStairs(int n) {
    	   	 if (n == 1) {
    	    	    return 1;
    	   	 }
    	   	 int[] dp = new int[n + 1];
    	   	 dp[1] = 1;
    	   	 dp[2] = 2;
    	  	  for (int i = 3; i <= n; i++) {
    	   	     dp[i] = dp[i - 1] + dp[i - 2];
    	  	  }
    	   	 return dp[n];
    		}


```
动态规划！学习！


