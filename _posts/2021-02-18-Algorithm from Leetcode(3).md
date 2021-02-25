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

## Maximum Profit in Job Scheduling(leetcode-1235)

You're given the startTime, endTime and profit arrays, return the maximum profit you can take such that there are no two jobs in the subset with overlapping time range.

#### Dynamic Programming & Binary Search
``` python
jobs = sorted(zip(startTime,endTime,profit), key=lambda x:x[1])
e_time = [e for _,e,_ in jobs]

for i in range(1, len(profits)):
    start, end, profit = jobs[i][0], jobs[i][1], jobs[i][2]

    dp[i] = dp[i-1]

    idx = bisect.bisect_right(e_time, start) - 1
    dp[i] = max(dp[i], (dp[idx] if idx >= 0 else 0) + profit)
```

It is a key to sort by startTime or endTime and store startTime or endTime in the dp array.