---
title:  "Algorithm"
excerpt: "Note"

categories:
  - Algorithm
tags:
  - Algorithm
---

## Kadanes Algorithm (Longest sum contiguous subarray)

``` python
for each elements in array:
    max_ending_here = max_ending_here + array[i]
    if max_ending_here < array[i]:
        max_ending_here = array[i]
    if max_value < max_ending_here:
        max_value = max_ending_here
```


