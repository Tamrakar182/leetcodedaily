# 283. Move Zeroes

Tags: #array #twopointers #easy 

### Problem Statement
Given an integer array `nums`, move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.

**Note** that you must do this in-place without making a copy of the array.

```Example
Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
```
### My Approach

```Python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        for i in nums:
            if i == 0:
                nums.remove(i)
                nums.append(i)
```
This was the first approach I thought of where we loop over the `nums` array once and if there is an element 0, we remove it and append it to the end of the list. However, I came up with another solution that gets rid of the loop.
```Python
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        if 0 in nums:
            count = nums.count(0)
            nums[:] = [i for i in nums if i!= 0]
            nums.extend([0]*count)
        
```
In this solution, first we check if there's 0 or not in the `nums` array and if there is, we count the number of zero's in `count`. Then, we change the `nums` array in place by using list comprehension *(Note: the `nums[:]` is required here since the default list comprehension would make a new array and point to that instead )* and remove all the zeros. Then using `extend()`, we add the zeros in the end, multipled by `count` for every zero we have.

### Personal Thoughts
This is another hacky solution since I mostly utilised python methods and functionality. Will try to solve using a more conventional approach on a later date.