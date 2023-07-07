#twopointers #string 

### Problem Statement
Given a string `s`, reverse only all the vowels in the string and return it.

The vowels are `'a'`, `'e'`, `'i'`, `'o'`, and `'u'`, and they can appear in both lower and upper cases, more than once.

```Example
Input: s = "leetcode"
Output: "leotcede"
```

### My approach

```Python
class Solution:
    def reverseVowels(self, s: str) -> str:
        i = 0
        j = len(s)-1
        vowel = "aeiouAEIOU"
        s = list(s)


        while i<j:
            if s[i] in vowel and s[j] in vowel:
                s[i], s[j] = s[j], s[i]
                j-=1
                i+=1
            elif s[i] in vowel:
                j-=1
            elif s[j] in vowel:
                i+=1
            else:
                i+=1
                j-=1
        s ="".join(map(str,s))
        return s
```


### Personal Thoughts
