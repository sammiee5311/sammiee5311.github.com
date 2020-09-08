---
title:  "Algorithm from leetcode(2)"
excerpt: "Note"

categories:
  - Algorithm
tags:
  - Algorithm
  - Leetcode
  
classes: wide

last_modified_at: 2020-09-06

---

## Partition Equal Subset Sum(leetcode-416)

Given a non-empty array containing only positive integers, find if the array can be partitioned into two subsets such that the sum of elements in both subsets is equal.

#### bottom-up
``` python
# with only one number, we can form a subset only when the required sum is
# equal to its value
for j in range(1, s + 1):
    dp[0][j] = nums[0] == j

# process all subsets for all sums
for i in range(1, numsLen):
    for j in range(1, s + 1):
        if dp[i - 1][j]:  # if we can get the sum 'j' without the number at index 'i'
            dp[i][j] = dp[i - 1][j]
        elif j >= nums[i]:  # else if we can find a subset to get the remaining sum
            dp[i][j] = dp[i - 1][j - nums[i]]
```

#### memoization+dfs
``` python
if remain in self.cache:
    return self.cache[remain]
if remain == 0:
    return True
if remain < 0 or i == len(self.nums):
    return False
self.cache[remain] = self.dfs(remain - self.nums[i], i + 1) or self.dfs(remain, i + 1)
return self.cache[remain]
```