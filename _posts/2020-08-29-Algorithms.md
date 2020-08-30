---
title:  "Algorithms from leetcode"
excerpt: "Note"

categories:
  - Algorithm
tags:
  - Algorithm
  - Leetcode
---

## Reverse Nodes in k-Group (leecode-25)

Given a linked list, reverse the nodes of a linked list k at a time and return its modified list.

``` python
node = next_head = ListNode(0)
node.next = head
start = end = head

while True:
    cnt = 0
    while end and cnt < k:
        end = end.next
        cnt += 1

    if cnt == k:
        prev, cur = end, start
        for _ in range(k):
            cur.next, prev, cur = prev, cur, cur.next

        next_head.next = prev
        next_head = start
        start = end
    else:
        return node.next
```

![](/assets/images/leetcode/leetcode_25.png)

Iterate the 'end' Kth time. Reverse nodes from 'start' untill right before 'end'.

## Combination Sum II (leecode-40)

Given a collection of candidate numbers (candidates) and a target number (target), find all unique combinations in candidates where the candidate numbers sums to target.

``` python
if target == 0:
    output.append(path[:])
    return

for i in range(index, len(candidates)):
    if target < candidates[i]:
        return
    if i > index and candidates[i] == candidates[i-1]:
        continue

    path.append(candidates[i])
    self.dfs(candidates, target-candidates[i], i+1, path, output)
    path.pop()
```

Use dfs to find the paths. By writing 'if target < candidates[i]:' in for iterations, it takes less time.

## Edit Distance (leetcode-72)

Given two words word1 and word2, find the minimum number of operations required to convert word1 to word2. <br>

You have the following 3 operations permitted on a word:
+ Insert a character
+ Delete a character
+ Replace a character

``` python
dp = [[0]*(a+1) for _ in range(b+1)]

for i in range(1,a+1):
    dp[0][i] = i

for i in range(1,b+1):
    dp[i][0] = i

for i in range(1,b+1):
    for j in range(1,a+1):
        if word1[j-1] == word2[i-1]:
            dp[i][j] = dp[i-1][j-1]
        else:
            dp[i][j] = min(dp[i-1][j],dp[i][j-1],dp[i-1][j-1]) + 1
```

![](/assets/images/leetcode/leetcode_72.png)

It is a key to find a sub problem.

[Reference from Youtube](https://www.youtube.com/watch?v=MiqoA-yF-0M)
{: .notice--info}