# 1768. Merge Strings Alternately

Topics: #twopointers #string #easy

### Problem Statement
You are given two strings `word1` and `word2`. Merge the strings by adding letters in alternating order, starting with `word1`. If a string is longer than the other, append the additional letters onto the end of the merged string.

Return _the merged string._

```Example
Input: word1 = "abc", word2 = "pqr"
Output: "apbqcr"
Explanation: The merged string will be merged as so:
word1:  a   b   c
word2:    p   q   r
merged: a p b q c r
```
### My Approach
```python
def mergeAlternately(word1: str, word2: str) -> str:
	emptyString = ""
	i = 0
	j = 0
	while(i<len(word1) and j<len(word2)):
		emptyString += word1[i]
		emptyString += word2[j]
		i += 1
		j += 1
	if len(word1)>len(word2):
		for k in range(i, len(word1)):
			emptyString += word1[k]
	else:
		for l in range(j, len(word2)):
			emptyString += word2[l]
	return emptyString
```
I used a while loop which appended the letters alternately in a new string ``emptyString``. Afterwards, I checked for the longer string and if any letters were left over, appended them to ``emptyString`` and returned it. 

### Personal Thoughts
This problem wasn't that hard but my solution wasn't the best as well. I couldv'e utilized python's inbuilt slicing methods to get rid of an extra loop and many more optimization strategies but well if it ain't broke, dont fix it. 