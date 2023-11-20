# 1679. Max Number of K-Sum Pairs

Tags: #array #twopointers #sorting #hashtable #medium 

### Problem Statement
You are given an integer array `nums` and an integer `k`.

In one operation, you can pick two numbers from the array whose sum equals `k` and remove them from the array.

Return _the maximum number of operations you can perform on the array_.

```Example
Input: nums = [1,2,3,4], k = 5
Output: 2
Explanation: Starting with nums = [1,2,3,4]:
- Remove numbers 1 and 4, then nums = [2,3]
- Remove numbers 2 and 3, then nums = []
There are no more pairs that sum up to 5, hence a total of 2 operations.
```

### My Approach
```Python
class Solution:
    def maxOperations(self, nums: List[int], k: int) -> int:
        i = 0
        j = len(nums)-1
        count = 0
        nums.sort()

        while(i<j):
            sum =nums[i]+nums[j] 
            if  sum == k:
                count +=1
                i+=1
                j-=1
            elif sum < k:
                i+=1
            else:
                j-=1
        return count
```

### Personal Thoughts