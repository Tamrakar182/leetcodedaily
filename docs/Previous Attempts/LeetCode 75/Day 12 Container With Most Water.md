# 11. Container With Most Water

Tags: #array #twopointers #greedy #medium 

### Problem Statement
You are given an integer array `height` of length `n`. There are `n` vertical lines drawn such that the two endpoints of the `ith` line are `(i, 0)` and `(i, height[i])`.

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return _the maximum amount of water a container can store_.

**Notice** that you may not slant the container.

![LeetCodeExample](https://s3-lc-upload.s3.amazonaws.com/uploads/2018/07/17/question_11.jpg)


```Example
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
```

### My Approach
```Python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        i = 0
        j = len(height)-1
        temp = 0
        primary = 0
        while(i<j):
            temp = min(height[i], height[j])*(j-i)
            if temp > primary:
                primary = temp
            if height[j]>height[i]:
                i+=1
            else:
                j-=1
        return primary
```


### Personal Thoughts