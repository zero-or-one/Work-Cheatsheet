# Algorithm Patterns Cheat Sheet

## Table of Contents

- [Sliding Window](#sliding-window)
- [Two Pointers](#two-pointers)
- [Fast & Slow Pointers](#fast--slow-pointers)
- [Merge Intervals](#merge-intervals)
- [Cyclic Sort](#cyclic-sort)
- [In-place Reversal of a Linked List](#in-place-reversal-of-a-linked-list)
- [Breadth-First Search (BFS)](#breadth-first-search-bfs)
- [Depth-First Search (DFS)](#depth-first-search-dfs)
- [Binary Search](#binary-search)
- [Topological Sort](#topological-sort)
- [Dijkstra’s Algorithm](#dijkstras-algorithm)
- [Bellman-Ford Algorithm](#bellman-ford-algorithm)
- [Floyd Warshall Algorithm](#floyd-warshall-algorithm)
- [References](#references)

---

## Sliding Window

Used to optimize problems involving contiguous subarrays or substrings.

**Common Problems:**

- Maximum sum of a subarray of size `k`
- Longest substring without repeating characters

**Time Complexity:** O(N)

```python
# Example: Find the maximum sum of a subarray of size k

def max_subarray_sum(arr, k):
    max_sum, window_sum = 0, 0
    left = 0
    for right in range(len(arr)):
        window_sum += arr[right]
        if right >= k - 1:
            max_sum = max(max_sum, window_sum)
            window_sum -= arr[left]
            left += 1
    return max_sum
```

---

## Two Pointers

Useful for searching pairs in a sorted array or linked list problems.

**Common Problems:**

- Pair with target sum
- Removing duplicates from a sorted array

**Time Complexity:** O(N)

```python
# Example: Two Sum (sorted array)

def two_sum(arr, target):
    left, right = 0, len(arr) - 1
    while left < right:
        current_sum = arr[left] + arr[right]
        if current_sum == target:
            return [left, right]
        elif current_sum < target:
            left += 1
        else:
            right -= 1
    return []
```

---

## Fast & Slow Pointers

Used to detect cycles in linked lists or determine the middle of a list.

**Common Problems:**

- Detect cycle in a linked list
- Find the middle of a linked list

**Time Complexity:** O(N)

```python
# Example: Detect cycle in a linked list

def has_cycle(head):
    slow, fast = head, head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            return True
    return False
```

---

## Merge Intervals

Used for interval merging problems.

**Common Problems:**

- Merge overlapping intervals
- Insert an interval into a sorted list

**Time Complexity:** O(N log N)

```python
# Example: Merge overlapping intervals

def merge_intervals(intervals):
    intervals.sort(key=lambda x: x[0])
    merged = []
    for interval in intervals:
        if not merged or merged[-1][1] < interval[0]:
            merged.append(interval)
        else:
            merged[-1][1] = max(merged[-1][1], interval[1])
    return merged
```

---

## Breadth-First Search (BFS)

Used in shortest path problems or level order traversal.

**Time Complexity:** O(V + E)

```python
# Example: BFS traversal
from collections import deque

def bfs(graph, start):
    queue = deque([start])
    visited = set([start])
    while queue:
        node = queue.popleft()
        print(node, end=' ')
        for neighbor in graph[node]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)
```

---

## Depth-First Search (DFS)

Used in tree traversals, cycle detection, and pathfinding.

**Time Complexity:** O(V + E)

```python
# Example: DFS traversal

def dfs(graph, node, visited=set()):
    if node in visited:
        return
    print(node, end=' ')
    visited.add(node)
    for neighbor in graph[node]:
        dfs(graph, neighbor, visited)
```

---

## Binary Search

Used for searching in sorted arrays.

**Time Complexity:** O(log N)

```python
# Example: Binary Search

def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```

---

## Topological Sort

Used for scheduling tasks and dependency resolution.

**Time Complexity:** O(V + E)

```python
# Example: Topological Sort using Kahn’s Algorithm
from collections import deque

def topological_sort(graph):
    in_degree = {node: 0 for node in graph}
    for node in graph:
        for neighbor in graph[node]:
            in_degree[neighbor] += 1
    queue = deque([node for node in in_degree if in_degree[node] == 0])
    order = []
    while queue:
        node = queue.popleft()
        order.append(node)
        for neighbor in graph[node]:
            in_degree[neighbor] -= 1
            if in_degree[neighbor] == 0:
                queue.append(neighbor)
    return order
```

---

## References

This document is inspired by the LeetCode patterns guide available at:

- [LeetCode Patterns Cheatsheet](https://leetcode.com/)
