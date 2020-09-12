---
title:  "Algorithm"
excerpt: "Note"

categories:
  - Algorithm
tags:
  - Algorithm
  
last_modified_at: 2020-08-30

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

## Topological Sorting Algorithm (geeksforgeeks)
 
``` python
def topologicalSortUtil(self,v,visited,stack): 

    # Mark the current node as visited. 
    visited[v] = True

    # Recur for all the vertices adjacent to this vertex 
    for i in self.graph[v]: 
        if visited[i] == False: 
            self.topologicalSortUtil(i,visited,stack) 

    # Push current vertex to stack which stores result 
    stack.insert(0,v)
```

## Kahn's Algorithm (geeksforgeeks)

``` python
def topologicalSort(self): 
    # Create a vector to store indegrees of all 
    # vertices. Initialize all indegrees as 0. 
    in_degree = [0]*(self.V) 

    # Traverse adjacency lists to fill indegrees of 
       # vertices.  This step takes O(V + E) time 
    for i in self.graph: 
        for j in self.graph[i]: 
            in_degree[j] += 1

    # Create an queue and enqueue all vertices with 
    # indegree 0 
    queue = [] 
    for i in range(self.V): 
        if in_degree[i] == 0: 
            queue.append(i) 

    # Initialize count of visited vertices 
    cnt = 0

    # Create a vector to store result (A topological 
    # ordering of the vertices) 
    top_order = [] 

    # One by one dequeue vertices from queue and enqueue 
    # adjacents if indegree of adjacent becomes 0 
    while queue: 
                        
        # Extract front of queue (or perform dequeue) 
        # and add it to topological order 
        u = queue.pop(0) 
        top_order.append(u) 

        # Iterate through all neighbouring nodes 
        # of dequeued node u and decrease their in-degree 
        # by 1 
        for i in self.graph[u]: 
            in_degree[i] -= 1
            # If in-degree becomes zero, add it to queue 
            if in_degree[i] == 0: 
                queue.append(i) 
        cnt += 1
```

## Convert a binary tree to a graph

``` python
def dfs(node, parent,graph):
    if not node:
        return

    if parent:
        graph[node].append(parent)

    if node.right:
        graph[node].append(node.right)
        dfs(node.right, node, graph)

    if node.left:
        graph[node].append(node.left)
        dfs(node.left, node, graph)
                
dfs(root,None,graph)
```


## Sieve_of_Eratosthenes

![](/assets/images/algorithm/Sieve_of_Eratosthenes.gif)

``` python
n = number # range of the number
a = [False,False] + [True]*(n-1)
primes = []

for i in range(2,n+1):
  if a[i]:
    primes.append(i)
    for j in range(2*i, n+1, i):
        a[j] = False
print(primes)
```