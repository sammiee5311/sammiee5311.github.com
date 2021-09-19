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

## Container With Most Water([leetcode-11](https://leetcode.com/problems/container-with-most-water/))

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

## Maximum Profit in Job Scheduling([leetcode-1235](https://leetcode.com/problems/maximum-profit-in-job-scheduling/))

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

## Range Sum Query - Mutable([leetcode-307](https://leetcode.com/problems/range-sum-query-mutable/))

``` python
# time complexity :  update : O(U*log(n)) / query : O(Q*log(n))
# space completxity : O(sizeof(tree)) == O(2**h)

class SegmentTree:
    def __init__(self, n, si, nums, left, right):
        h = int(math.ceil(math.log(n) / math.log(2)))
        size = 2*int(2**h + 1)
        self.tree = [0] * (2*size)
        self.build_tree(si, nums, left, right)

    def build_tree(self, si, nums, left, right):
        if left == right:
            self.tree[si] = nums[left]
            return nums[left]

        mid = (left + right) // 2
        self.tree[si] = self.build_tree(2*si+1, nums, left, mid) + self.build_tree(2*si+2, nums, mid+1, right)

        return self.tree[si]

    def query(self, si, sl, sr, left, right):
        if left <= sl and sr <= right:
            return self.tree[si]

        if left > sr or sl > right:
            return 0

        mid = (sl + sr) // 2
        return self.query(2*si+1, sl, mid, left, right) + self.query(2*si+2, mid+1, sr, left, right)

    def update(self, si, sl, sr, idx, diff):
        if idx < sl or sr < idx:
            return

        self.tree[si] += diff

        if sl != sr:
            mid = (sl + sr) // 2
            self.update(2*si+1, sl, mid, idx, diff)
            self.update(2*si+2, mid+1, sr, idx, diff)
```

Implementing a Segment Tree is the key.

## Maximum Width Ramp([leetcode-962](https://leetcode.com/problems/maximum-width-ramp/))

A ramp in an integer array nums is a pair (i, j) for which i < j and nums[i] <= nums[j]. The width of such a ramp is j - i.

#### Heap
``` python
# time complexity : O(nlogn)
# space complexity : O(n)

while heap:
    cur_val, cur_idx = heapq.heappop(heap)

    if idx < cur_idx:
        maxi = max(maxi, cur_idx - idx)
    elif idx > cur_idx:
        val = cur_val
        idx = cur_idx
```

#### Bisect
``` python
# time complexity : O(nlogn)
# space complexity : O(n)

for i in range(n-2, -1, -1):
    idx = bisect_left(right_maxes, (nums[i], -1))
    if idx == len(right_maxes):
        right_maxes.append((nums[i], i))
    else:
        res = max(res, right_maxes[idx][1] - i)
```

#### monotonic stack
``` python
# time complexity : O(n) (worst case O(n2))
# space complexity : O(n)

s = []
for i in range(len(nums)):
    if not s or nums[i] < nums[s[-1]]:
        s.append(i)
ans = 0
for i in range(len(nums) - 1, -1, -1):
    while s and nums[s[-1]] <= nums[i]:
        ans = max(ans, i - s.pop())
```

## Maximum Earnings From Taxi([leetcode-2008](https://leetcode.com/problems/maximum-earnings-from-taxi/))

``` python
# time complexity :  O(nlog(n))
# space completxity : O(nlog(n))

def dp(idx, memo):
    if idx >= n:
        return 0

    if idx not in memo:
        ans = dp(idx+1, memo)

        s, e, t = rides[idx]

        j = bisect_left(rides, [e, 0, 0])

        ans = max(ans, e - s + t + dp(j, memo))

        memo[idx] = ans

    return memo[idx]
```

It is a key to use binary search not to get TLE.
