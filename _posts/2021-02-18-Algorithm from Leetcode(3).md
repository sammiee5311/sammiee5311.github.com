---
title:  "Algorithm from leetcode(3)"
excerpt: "Note"

categories:
  - Algorithm
tags:
  - Algorithm
  - Leetcode
  
classes: wide

last_modified_at: 2021-02-18

---

## Container With Most Water(leetcode-11)

Find two lines, which, together with the x-axis forms a container, such that the container contains the most water.

#### Brute Force
``` python
for right in range(1,len(heights)):
    for left in range(right):
        h = min(heights[right], heights[left])
        res = max(res, h*(right-left))
```

#### Two Pointer
``` python
while left < right:
    h = min(heights[left], heights[right])
    res = max(res, h*(right-left))
    
    if heights[left] > heights[right]:
        right -= 1
    else:
        left += 1
```