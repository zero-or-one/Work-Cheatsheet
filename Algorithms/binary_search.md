🔍 Binary Search Documentation
# Binary Search
## Definition

Binary Search is a search algorithm used to find the position of a target value within a sorted array. It works by repeatedly dividing the search interval in half. 

## Time Complexity

- **Best Case:** O(1)
- **Average and Worst Case:** O(log n)

## How Binary Search Works

Given a sorted array `arr` and a target value to search for:

1. Find the middle element of the array.
2. If the middle element equals the target, return its index.
3. If the target is smaller than the middle element, search the left half of the array.
4. If the target is larger than the middle element, search the right half of the array.
5. Repeat the process until the target is found or the search space is exhausted.

## Implementation

Below is a Python implementation of Binary Search:

```python
def binary_search(arr, target):
    """
    Perform binary search on a sorted array to find the index of the target value.

    Args:
        arr (list): A sorted list of elements to search.
        target (int or float): The value to search for in the array.

    Returns:
        int: The index of the target value in the array if found; otherwise, -1.

    Example:
        >>> arr = [1, 3, 5, 7, 9]
        >>> binary_search(arr, 5)
        2
        >>> binary_search(arr, 4)
        -1
    """
    left, right = 0, len(arr) - 1

    while left <= right:
        mid = (left + right) // 2  # Find the middle element
        if arr[mid] == target:
            return mid  # Target found, return its index
        elif arr[mid] < target:
            left = mid + 1  # Search in the right half
        else:
            right = mid - 1  # Search in the left half

    return -1  # Target not found

# Example usage:
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9]
binary_search(arr, 7) # 6
binary_search(arr, 13) # -1
```

