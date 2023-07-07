# 1431. Kids With the Greatest Number of Candies

Tags: #array #easy

### Problem Statement
There are `n` kids with candies. You are given an integer array `candies`, where each `candies[i]` represents the number of candies the `ith` kid has, and an integer `extraCandies`, denoting the number of extra candies that you have.

Return _a boolean array_ `result` _of length_ `n`_, where_ `result[i]` _is_ `true` _if, after giving the_ `ith` _kid all the_ `extraCandies`_, they will have the **greatest** number of candies among all the kids__, or_ `false` _otherwise_.

Note that **multiple** kids can have the **greatest** number of candies.

```Example
Input: candies = [4,2,1,1,2], extraCandies = 1
Output: [true,false,false,false,false] 
Explanation: There is only 1 extra candy.
Kid 1 will always have the greatest number of candies, even if a different kid is given the extra candy.
```
### My approach
```Python
def func(candies, extraCandies):
    maximum = max(candies)
    result = [False for i in candies]
    for i in range(len(candies)):
        x = candies[i]
        if x+extraCandies >= maximum:
            result[i] = True
    return result
```
Here, first I take the **maximum** from the candies and also initialise an array of Falses into **result** the size of **candies** list. Then, I check each candy **x** against the maximum and convert the candy's position as True in the **result**.

```Python
import numpy as np

def func(candies, extraCandies):
    np_array = np.array(candies)
    return ((np_array+extraCandies) >= extraCandies)
```
This is another approach that I thought of using the **numpy** package since it just natively returned a Boolean array when a condition is passed to a **numpy.array**.

### Personal Thoughts
This problem wasn't that difficult and was fairly obvious once you thought about it. And about using external libraries, I'm totally fine with using them even though they might obfuscate the underlying logic and add an abstraction layer.