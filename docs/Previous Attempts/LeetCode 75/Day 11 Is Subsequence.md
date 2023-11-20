# 392. Is Subsequence

Tags: #twopointers #string #dynamicprogramming #easy 

### Problem Statement
Given two strings `s` and `t`, return `true` _if_ `s` _is a **subsequence** of_ `t`_, or_ `false` _otherwise_.

A **subsequence** of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., `"ace"` is a subsequence of `"abcde"` while `"aec"` is not).

```Example
Input: s = "axc", t = "ahbgdc"
Output: false

Input: s = "abc", t = "ahbgdc"
Output: true
```
### My approach
```Python
class Solution:
    def isSubsequence(self, s: str, t: str) -> bool:
        r=0
        if s=="":
            return True
        for i in t:
            if r<len(s) and s[r] == i:
                r+=1
        return r==len(s)
```
In this solution, first we check if the subsequent string is empty upon which it will be a subsequence no matter what. Then we loop over `t`, the string to be checked against and if `r` is less than the length of `s` (*this prevents a list out of index exception*) and the current element is same as `s`'s `rth` item then, we increment r. Finally, we check if `r` is equal to the assumed subsequence length, returning `True` or `False`. 

### Personal Thoughts
This was a rather simple approach suggested by one of our classmates when I was thinking of a more complex one involving two loops.