# 334. Increasing Triplet Subsequence

Tags: #array #greedy #medium 

### Problem Statement
Given an integer array `nums`, return `true` _if there exists a triple of indices_ `(i, j, k)` _such that_ `i < j < k` _and_ `nums[i] < nums[j] < nums[k]`. If no such indices exists, return `false`.

**Follow up:** Could you implement a solution that runs in `O(n)` time complexity and `O(1)` space complexity?

```Example
Input: nums = [2,1,5,0,4,6]
Output: true
Explanation: The triplet (3, 4, 5) is valid because nums[3] == 0 < nums[4] == 4 < nums[5] == 6.
```

### My approach
```Python
class Solution:
    def increasingTriplet(self, nums):
        f = float('inf')
        s = float('inf')
        
        for n in nums:
            if n <= f:
                f = n
            elif n <= s:
                s = n
            else:
                return True
        
        return False
```
In this solution, first we intialise two variable `f` and `s` to be infinity. Then, we loop over the nums array and compare the current element if it's smaller then `f`. Certainly in the first iteration, `n` will be smaller than `f` so, `f` is now assigned to be the current element. In the next iteration, we again check the condition and keep the smaller of the element in `f` *(this means the smallest element will be in `f`)* otherwise we reassign to `s` *(this means that the element just larger to `f` will be in `s`)* . Once again, checking through the conditions, if there are no more elements greater than f and s then we return `True` since our triplets condition is satisfied otherwise we return `False`.

### Personal Thoughts
I couldn't come up with a solution to this problem on my own and had to go through the discussions tab in order to do this solution. I will come back to this problem once again, and try to solve this myself on a later date.