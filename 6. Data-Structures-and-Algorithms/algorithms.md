# Algorithm Templates and Explanations

This document contains code templates for common algorithms and data structures, along with brief explanations and complexity analysis.

## Two Pointers

### One Input, Opposite Ends

```python
def fn(arr):
    left = ans = 0
    right = len(arr) - 1

    while left < right:
        # do some logic here with left and right
        if CONDITION:
            left += 1
        else:
            right -= 1

    return ans
```

**Explanation:** This pattern is useful for problems where you need to find a pair of elements in a sorted array that satisfy a certain condition. The pointers start at opposite ends and move towards each other.

**Time Complexity:** O(n)
**Space Complexity:** O(1)

### Two Inputs, Exhaust Both

```python
def fn(arr1, arr2):
    i = j = ans = 0

    while i < len(arr1) and j < len(arr2):
        # do some logic here
        if CONDITION:
            i += 1
        else:
            j += 1

    while i < len(arr1):
        # do logic
        i += 1

    while j < len(arr2):
        # do logic
        j += 1

    return ans
```

**Explanation:** This pattern is used when you need to process two sorted arrays simultaneously. The pointers move through each array based on the condition.

**Time Complexity:** O(n + m)
**Space Complexity:** O(1)

## Sliding Window

```python
def fn(arr):
    left = ans = curr = 0

    for right in range(len(arr)):
        # do logic here to add arr[right] to curr

        while WINDOW_CONDITION_BROKEN:
            # remove arr[left] from curr
            left += 1

        # update ans

    return ans
```

**Explanation:** The sliding window technique is used to find subarrays or substrings that satisfy a certain condition. The window expands and contracts based on the condition.

**Time Complexity:** O(n)
**Space Complexity:** O(1)

## Build a Prefix Sum

```python
def fn(arr):
    prefix = [arr[0]]
    for i in range(1, len(arr)):
        prefix.append(prefix[-1] + arr[i])

    return prefix
```

**Explanation:** Prefix sums are useful for quickly calculating the sum of any subarray. The prefix array stores the cumulative sum up to each index.

**Time Complexity:** O(n)
**Space Complexity:** O(n)

## Efficient String Building

```python
def fn(arr):
    ans = []
    for c in arr:
        ans.append(c)

    return "".join(ans)
```

**Explanation:** This pattern is used to efficiently build strings by appending characters to a list and then joining them.

**Time Complexity:** O(n)
**Space Complexity:** O(n)

## Linked List: Fast and Slow Pointer

```python
def fn(head):
    slow = head
    fast = head
    ans = 0

    while fast and fast.next:
        # do logic
        slow = slow.next
        fast = fast.next.next

    return ans
```

**Explanation:** The fast and slow pointer technique is used to find the middle of a linked list or detect cycles.

**Time Complexity:** O(n)
**Space Complexity:** O(1)

## Reversing a Linked List

```python
def fn(head):
    curr = head
    prev = None
    while curr:
        next_node = curr.next
        curr.next = prev
        prev = curr
        curr = next_node

    return prev
```

**Explanation:** This pattern is used to reverse a linked list in-place.

**Time Complexity:** O(n)
**Space Complexity:** O(1)

## Find Number of Subarrays That Fit an Exact Criteria

```python
from collections import defaultdict

def fn(arr, k):
    counts = defaultdict(int)
    counts[0] = 1
    ans = curr = 0

    for num in arr:
        # do logic to change curr
        ans += counts[curr - k]
        counts[curr] += 1

    return ans
```

**Explanation:** This pattern is used to find the number of subarrays that sum to a specific value using a hash map to store prefix sums.

**Time Complexity:** O(n)
**Space Complexity:** O(n)

## Monotonic Stack

```python
def fn(arr):
    stack = []
    ans = 0

    for num in arr:
        # for monotonic decreasing, just flip the > to <
        while stack and stack[-1] > num:
            # do logic
            stack.pop()
        stack.append(num)

    return ans
```

**Explanation:** A monotonic stack is used to maintain a stack of elements in increasing or decreasing order, useful for problems involving next greater/smaller elements.

**Time Complexity:** O(n)
**Space Complexity:** O(n)

## Binary Tree: DFS (Recursive)

```python
def dfs(root):
    if not root:
        return

    ans = 0

    # do logic
    dfs(root.left)
    dfs(root.right)
    return ans
```

**Explanation:** Recursive DFS is used to traverse a binary tree, performing some logic at each node.

**Time Complexity:** O(n)
**Space Complexity:** O(h) (where h is the height of the tree)

## Binary Tree: DFS (Iterative)

```python
def dfs(root):
    stack = [root]
    ans = 0

    while stack:
        node = stack.pop()
        # do logic
        if node.left:
            stack.append(node.left)
        if node.right:
            stack.append(node.right)

    return ans
```

**Explanation:** Iterative DFS uses a stack to simulate the recursive call stack, useful for avoiding recursion depth limits.

**Time Complexity:** O(n)
**Space Complexity:** O(h)

## Binary Tree: BFS

```python
from collections import deque

def fn(root):
    queue = deque([root])
    ans = 0

    while queue:
        current_length = len(queue)
        # do logic for current level

        for _ in range(current_length):
            node = queue.popleft()
            # do logic
            if node.left:
                queue.append(node.left)
            if node.right:
                queue.append(node.right)

    return ans
```

**Explanation:** BFS is used to traverse a binary tree level by level, useful for problems involving level-order traversal.

**Time Complexity:** O(n)
**Space Complexity:** O(n)

## Graph: DFS (Recursive)

```python
def fn(graph):
    def dfs(node):
        ans = 0
        # do some logic
        for neighbor in graph[node]:
            if neighbor not in seen:
                seen.add(neighbor)
                ans += dfs(neighbor)

        return ans

    seen = {START_NODE}
    return dfs(START_NODE)
```

**Explanation:** Recursive DFS is used to traverse a graph, performing some logic at each node.

**Time Complexity:** O(V + E)
**Space Complexity:** O(V)

## Graph: DFS (Iterative)

```python
def fn(graph):
    stack = [START_NODE]
    seen = {START_NODE}
    ans = 0

    while stack:
        node = stack.pop()
        # do some logic
        for neighbor in graph[node]:
            if neighbor not in seen:
                seen.add(neighbor)
                stack.append(neighbor)

    return ans
```

**Explanation:** Iterative DFS uses a stack to simulate the recursive call stack, useful for avoiding recursion depth limits.

**Time Complexity:** O(V + E)
**Space Complexity:** O(V)

## Graph: BFS

```python
from collections import deque

def fn(graph):
    queue = deque([START_NODE])
    seen = {START_NODE}
    ans = 0

    while queue:
        node = queue.popleft()
        # do some logic
        for neighbor in graph[node]:
            if neighbor not in seen:
                seen.add(neighbor)
                queue.append(neighbor)

    return ans
```

**Explanation:** BFS is used to traverse a graph level by level, useful for finding the shortest path in unweighted graphs.

**Time Complexity:** O(V + E)
**Space Complexity:** O(V)

## Find Top K Elements with Heap

```python
import heapq

def fn(arr, k):
    heap = []
    for num in arr:
        # do some logic to push onto heap according to problem's criteria
        heapq.heappush(heap, (CRITERIA, num))
        if len(heap) > k:
            heapq.heappop(heap)

    return [num for num in heap]
```

**Explanation:** This pattern is used to find the top K elements in an array using a min-heap or max-heap.

**Time Complexity:** O(n log k)
**Space Complexity:** O(k)

## Binary Search

```python
def fn(arr, target):
    left = 0
    right = len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            # do something
            return
        if arr[mid] > target:
            right = mid - 1
        else:
            left = mid + 1

    # left is the insertion point
    return left
```

**Explanation:** Binary search is used to find an element in a sorted array or the insertion point for a target value.

**Time Complexity:** O(log n)
**Space Complexity:** O(1)

## Binary Search: Duplicate Elements, Left-Most Insertion Point

```python
def fn(arr, target):
    left = 0
    right = len(arr)
    while left < right:
        mid = (left + right) // 2
        if arr[mid] >= target:
            right = mid
        else:
            left = mid + 1

    return left
```

**Explanation:** This variant of binary search finds the left-most insertion point in an array with duplicate elements.

**Time Complexity:** O(log n)
**Space Complexity:** O(1)

## Binary Search: Duplicate Elements, Right-Most Insertion Point

```python
def fn(arr, target):
    left = 0
    right = len(arr)
    while left < right:
        mid = (left + right) // 2
        if arr[mid] > target:
            right = mid
        else:
            left = mid + 1

    return left
```

**Explanation:** This variant of binary search finds the right-most insertion point in an array with duplicate elements.

**Time Complexity:** O(log n)
**Space Complexity:** O(1)

## Binary Search: For Greedy Problems

```python
def fn(arr):
    def check(x):
        # this function is implemented depending on the problem
        return BOOLEAN

    left = MINIMUM_POSSIBLE_ANSWER
    right = MAXIMUM_POSSIBLE_ANSWER
    while left <= right:
        mid = (left + right) // 2
        if check(mid):
            right = mid - 1
        else:
            left = mid + 1

    return left
```

**Explanation:** This pattern is used for problems where you need to find the minimum or maximum value that satisfies a certain condition.

**Time Complexity:** O(log n)
**Space Complexity:** O(1)

## Backtracking

```python
def backtrack(curr, OTHER_ARGUMENTS...):
    if (BASE_CASE):
        # modify the answer
        return

    ans = 0
    for (ITERATE_OVER_INPUT):
        # modify the current state
        ans += backtrack(curr, OTHER_ARGUMENTS...)
        # undo the modification of the current state

    return ans
```

**Explanation:** Backtracking is used to explore all possible solutions by building candidates incrementally and abandoning them if they don't satisfy the condition.

**Time Complexity:** O(2^n) (typically exponential)
**Space Complexity:** O(n)

## Dynamic Programming: Top-Down Memoization

```python
def fn(arr):
    def dp(STATE):
        if BASE_CASE:
            return 0

        if STATE in memo:
            return memo[STATE]

        ans = RECURRENCE_RELATION(STATE)
        memo[STATE] = ans
        return ans

    memo = {}
    return dp(STATE_FOR_WHOLE_INPUT)
```

**Explanation:** Top-down DP with memoization is used to solve problems by breaking them down into subproblems and caching the results to avoid redundant calculations.

**Time Complexity:** O(n) (depends on the problem)
**Space Complexity:** O(n)

## Build a Trie

```python
class TrieNode:
    def __init__(self):
        self.data = None
        self.children = {}

def fn(words):
    root = TrieNode()
    for word in words:
        curr = root
        for c in word:
            if c not in curr.children:
                curr.children[c] = TrieNode()
            curr = curr.children[c]
        # at this point, you have a full word at curr
        # you can perform more logic here to give curr an attribute if you want

    return root
```

**Explanation:** A trie is a tree-like data structure used to store strings, useful for prefix-based searches.

**Time Complexity:** O(m _ n) (where m is the length of the longest word and n is the number of words)
**Space Complexity:** O(m _ n)

## Dijkstra's Algorithm

```python
from math import inf
from heapq import *

distances = [inf] * n
distances[source] = 0
heap = [(0, source)]

while heap:
    curr_dist, node = heappop(heap)
    if curr_dist > distances[node]:
        continue

    for nei, weight in graph[node]:
        dist = curr_dist + weight
        if dist < distances[nei]:
            distances[nei] = dist
            heappush(heap, (dist, nei))
```

**Explanation:** Dijkstra's algorithm is used to find the shortest path from a source node to all other nodes in a weighted graph.

**Time Complexity:** O((V + E) log V)
**Space Complexity:** O(V)

## References

- [LICC Algorithm Templates](https://leetcode.com/explore/interview/card/cheatsheets/720/resources/4723/)
