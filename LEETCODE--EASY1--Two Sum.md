#LEETCODE--EASY1--Two Sum
---
题目描述：

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].

---
我的python实现

···

	nums = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
	target = 11

	a = len(nums)
	i = 0
	while i < a:
    	j = i + 1
    	while j < a:
        	if nums[i] + nums[j] == target:
            print(i, j)
        j = j + 1
    i = i + 1
···

大佬的代码

···

	def twoSum(self, nums, target):
        seen = {}
        for i, v in enumerate(nums):
            remaining = target - v
            if remaining in seen:
                return [seen[remaining], i]
            seen[v] = i
        return []

···


总结：虽然的确实现了所要求的功能，但是时间以及空间的花费上很大，和其他大佬的代码相比，显得很幼稚，很僵硬，没有想到怎么去降低代码的时间空间复杂度，仍需多加练习！！！
1.enumerate（）和dictionary的灵活运用
2.remaining = target - v   不要思维定势


