#twopointers #string

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
        a = " ".join(s.split()).split(" ")
        if ( len(a) == 1):
            return s
        return " ".join(a[::-1])
        
```

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

### Personal Thoughts
