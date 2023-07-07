#array #greedy

### Problem Statement
You have a long flowerbed in which some of the plots are planted, and some are not. However, flowers cannot be planted in **adjacent** plots.

Given an integer array `flowerbed` containing `0`'s and `1`'s, where `0` means empty and `1` means not empty, and an integer `n`, return `true` _if_ `n` _new flowers can be planted in the_ `flowerbed` _without violating the no-adjacent-flowers rule and_ `false` _otherwise_.

```Example
Input: flowerbed = [1,0,0,0,1], n = 2
Output: false
```

### My approach
```Python
def func(array, n):
    count = 0
    i = 0
    while i<len(array):
        if array[i] == 1 or array[i+1]==1 or array[i+2]==1:
            i+=1
        else:
            count +=1
            i+=2
    if count == n:
        return True
    return False
```


### Personal Thoughts

