# 345. Reverse Vowels of a String

Tags: #twopointers #string #easy

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
In my approach, first I took a ``vowel`` string to check against every list item. In a while loop, I checked whether the current element and the last element was in the vowels list, upon which if the condition was True, I swapped them and incremented ``i`` and decremented ``j``. For the other condition, if we only found vowel match in the current element then, we increment ``i`` otherwise if we only found in the last element then, we decrement ``j``. Finally, if none of those conditions match, then we increment both ``i`` and ``j`` to reach over to the next element. Finally, we join the array of character and return it as a string.

### Personal Thoughts
This was another wonderful solution presented by one of my friends which was implemented. Collaborative problem solving is very effective and can help to solve problem effectively by brainstroming.