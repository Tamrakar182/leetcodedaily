#Math #string 

### Problem Statement
For two strings `s` and `t`, we say "`t` divides `s`" if and only if `s = t + ... + t` (i.e., `t` is concatenated with itself one or more times).

Given two strings `str1` and `str2`, return _the largest string_ `x` _such that_ `x` _divides both_ `str1` _and_ `str2`.

```Example
Input: str1 = "ABCABC", str2 = "ABC"
Output: "ABC"
```
### My approach
```Python
class Solution:
    def gcdOfStrings(self, str1: str, str2: str) -> str:
        l1 = len(str1)
        l2 = len(str2)
        gcd = ""
        if l1<l2:
            str1, str2 = str2, str1
        for i in range(l2):
            if i == 0:
                temp = str2[0]
            else:
                temp = str2[:i+1]
            factor1 = len(str1)//len(temp) 
            factor2 = len(str2)//len(temp)
            if temp*factor1 == str1 and temp*factor2== str2:
                gcd = temp
        return gcd
```
So, here what I did is, at first I took the sizes of two string in **l1** and **l2** and also initialised an empty **gcd**. Comparing the two string's length, I made it so that **str1** was the longer of the two strings always. Then in a for loop, I checked if it's the first element, and stored in the **temp** otherwise took all the element up until i and stored it. Afterthat, I calculated the **factor1** and **factor2** which represents how many times, **temp** can fit into **str2** without any remainders. Finally, I checked if **temp** is a common divisor of both **str1** and **str2**, upon which we have gotten our Greatest Common Divisor upon the completion of the loop. In the end, we return **gcd**.

### Personal Thoughts
This question was my first forte into actually reading into what the question actually says and I had to think long and hard before attempting anything. Unfortunately, I wasn't able to solve this problem alone and took some help from a friend but well collaboration is key in coding. On to the next one!!!