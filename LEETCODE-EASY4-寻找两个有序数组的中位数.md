#LEETCODE-EASY4-寻找两个有序数组的中位数
---
给定两个大小为 m 和 n 的有序数组 nums1 和 nums2。

请你找出这两个有序数组的中位数，并且要求算法的时间复杂度为 O(log(m + n))。

你可以假设 nums1 和 nums2 不会同时为空。

示例 1:

nums1 = [1, 3]
nums2 = [2]

则中位数是 2.0
示例 2:

nums1 = [1, 2]
nums2 = [3, 4]

则中位数是 (2 + 3)/2 = 2.5
---
##myCode
```

	class Solution:
    	def findMedianSortedArrays(self, nums1: List[int], 	nums2: List[int]) -> float:
    	    nums3 = nums1 + nums2
    	    nums3 = sorted(nums3)
    	    a = len(nums3)
    	    if a % 2 == 1:
    	        c = float(nums3[int((a - 1) / 2)])
    	    else:
    	        c = (nums3[int(a/2)]+nums3[int(a/2-1)])/2
    	    return c
```

执行用时 :120 ms
内存消耗 :14 MB

不是很明白为什么会这么慢

执行用时为 52 ms 的范例：

```

	class Solution:
    	def findMedianSortedArrays(self, nums1: List[int], 	nums2: List[int]) -> float:
        	m = len(nums1)
        	n = len(nums2)
        	t = (m + n) / 2
        	it = int(t)
        	if t > it:
        	    b = e = it
        	else:
        	    b = it - 1
        	    e = it
        	tmp = nums1 + nums2
        	tmp.sort()
        	if b == e:
        	    return tmp[b]
        	return (tmp[b] + tmp[e]) / 2
```

我感觉我的和他的意思是一样的做法也一样，但是为啥那么慢呢？
难道是int()?
  
执行用时为 44 ms 的大佬范例：   

```

	class Solution:
    	def findMedianSortedArrays(self, nums1: List[int], 	nums2: List[int]) -> float:
    	    m, n = len(nums1), len(nums2)
    	    if m>n:
    	        nums1, nums2, m, n = nums2, nums1, n, m
    	    imin = 0
    	    imax = m
    	    halflen = (m+n+1)//2
    	    while imin<=imax:
    	        i = (imin + imax)//2
    	        j = halflen - i
    	        if i<m and nums1[i]<nums2[j-1]:
    	            imin += 1
    	        elif i>0 and nums1[i-1]>nums2[j]:
    	            imax -= 1
    	        else:
    	            if i==0:
    	                max_left = nums2[j-1]
    	            elif j==0:
    	                max_left = nums1[i-1]
    	            else:
    	                max_left = max([nums1[i-1], nums2	[j-1]])
    	            if (m+n)%2==1:
    	                return max_left
    	            if i==m:
    	                min_right = nums2[j]
    	            elif j==n:
    	                min_right = nums1[i]
    	            else:
    	                min_right = min([nums1[i], nums2	[j]])
    	            return (max_left+min_right)/2.0   
```

大佬的代码把我看傻了，这可能就是算法的重要性吧~
努力！加油！	
