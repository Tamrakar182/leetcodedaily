# 151. Reverse Words in a String

Tags: #twopointers #string #medium

### Problem Statement
Given an input string `s`, reverse the order of the **words**.

A **word** is defined as a sequence of non-space characters. The **words** in `s` will be separated by at least one space.

Return _a string of the words in reverse order concatenated by a single space._

**Note** that `s` may contain leading or trailing spaces or multiple spaces between two words. The returned string should only have a single space separating the words. Do not include any extra spaces.

```Example
Input: s = "  hello world  "
Output: "world hello"
Explanation: Your reversed string should not contain leading or trailing spaces.
```

### My approach
```Python
class Solution:
    def reverseWords(self, s: str) -> str:
        a = s.split()
        if ( len(a) == 1):
            return s
        return " ".join(a[::-1])
        
```
In my approach, I kinda cheated for this problem since I used python's built in methods to first split the given string into an array of words using ``s.split()`` and then checked if the length of the array was 1, if it was returned the original string otherwise I first reversed the array through ``a[::-1]`` and then used ``" ".join()`` to add the spaces in between words and return a string.
```Python
class Solution:
    def reverseWords(self, s: str) -> str:
        i = 0
        j = len(s)-1
		# Remove Front Spaces
        while i < len(s) and s[i] == " ":
            i += 1
		# Remove back spaces
        while j >= 0 and s[j] == " ":
            j -= 1
        ans = []
		# run while we dont get to initial valid index i
        while j >= i:
			# Trim middle spaces
            while j >= i and s[j] == " ":
                j -= 1
			# Make  word reverse it 
            temp = []
            while j >= i and s[j] != " ":
                temp.append(s[j])
                j -= 1
			# Append word to original ans
            ans.append("".join(temp[::-1]))
        return " ".join(ans)
```
Although my approach isn't the modal solution for the problem, I have found this solution which matches the LeetCode Description and solves the problem statement using the two pointer approach. The code comments pretty much explain the code.

### Personal Thoughts
Well even though I took the more hacky approach, I do think it is a valid solution to the problem since there were no restrictions in the problem statement *(Foreshadowing)*. I learned a lot too by going through the other solution that's why I included it here.