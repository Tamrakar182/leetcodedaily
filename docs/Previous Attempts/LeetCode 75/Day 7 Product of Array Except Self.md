# 238. Product of Array Except Self

Tags: #array #prefixsum #medium

### Problem Statement
Given an integer array `nums`, return _an array_ `answer` _such that_ `answer[i]` _is equal to the product of all the elements of_ `nums` _except_ `nums[i]`.

The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.

***You must write an algorithm that runs in `O(n)` time and without using the division operation.***

```Example
Input: nums = [-1,1,0,-3,3]
Output: [0,0,9,0,0]
```

### My approach
```Python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        length = len(nums)
        result = [1] * length  
        leftProduct = 1
        for i in range(length):
            result[i] *= leftProduct 
            leftProduct *= nums[i]  
        rightProduct = 1
        for i in range(length - 1, -1, -1):
            result[i] *= rightProduct  
            rightProduct *= nums[i] 
        return result

```


### Personal Thoughts
This question was quite hard, not due to the problem statement but due to the restriction of both O(n) time complexity and no division operation.