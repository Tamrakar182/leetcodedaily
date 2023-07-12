# 443. String Compression

Tags: #string #twopointers #medium 

### Problem Statement
Given an array of characters `chars`, compress it using the following algorithm:

Begin with an empty string `s`. For each group of **consecutive repeating characters** in `chars`:

- If the group's length is `1`, append the character to `s`.
- Otherwise, append the character followed by the group's length.

The compressed string `s` **should not be returned separately**, but instead, be stored **in the input character array `chars`**. Note that group lengths that are `10` or longer will be split into multiple characters in `chars`.

After you are done **modifying the input array,** return _the new length of the array_.

You must write an algorithm that uses only constant extra space.

```Example
Input: chars = ["a","b","b","b","b","b","b","b","b","b","b","b","b"]
Output: Return 4, and the first 4 characters of the input array should be: ["a","b","1","2"].
Explanation: The groups are "a" and "bbbbbbbbbbbb". This compresses to "ab12".
```

### My approach
```Python
class Solution:
    def compress(self, chars: List[str]) -> int:
        result = ""
        if len(chars) == 1:
            return 1
        chars.append(" ")
        count = 0
        current = chars[0]
        for i in range(len(chars)):
            if current == chars[i]:
                count +=1
            else:
                if count == 1:
                    result += chars[i-1]
                else:
                    result += chars[i-1] + str(count)
                current = chars[i]
                count = 1
        chars.clear()
        chars.extend(result)
        return len(chars)
```

### Personal Thoughts
This is kind of a workaround solution that carefully tread around the requirement of constant extra space. I did use a new variable however in the end, changed the existing `chars` to be modified instead.