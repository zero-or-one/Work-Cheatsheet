 Queue
Definition

A Queue follows the FIFO (First In, First Out) principle. It is used in scheduling algorithms and handling requests in servers.
Time Complexity

    Enqueue (Insert): O(1)
    Dequeue (Remove): O(1)

Example in Python

```python

from collections import deque

queue = deque()  # Initialize a queue
queue.append(1)  # Enqueue
queue.append(2)
print(queue.popleft())  # Dequeue -> Output: 1
```