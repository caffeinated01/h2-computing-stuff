A "divide and conquer" algorithm that finds the position of a target value within a **sorted list**

### Time Complexity

| Case             | Complexity | Description                                                                               |
| ---------------- | ---------- | ----------------------------------------------------------------------------------------- |
| **Best Case**    | `O(1)`     | The target item is the middle element                                                     |
| **Worst Case**   | `O(log n)` | The target is not in the list, requiring the list to be divided until one element remains |
| **Average Case** | `O(log n)` | The number of comparisons grows logarithmically with the list size                        |

### Implementation
#### Iterative

```python
def binarysearch(arr, target):
    l = 0
    r = len(arr) - 1

    while l <= r:  # left and right ptrs cannot cross
        mid = (l+r) // 2

        if arr[mid] == target:
            return mid # target found

        elif target > arr[mid]:
            l = mid + 1  # reduce search range
        elif target < arr[mid]:
            r = mid - 1  # reduce search range

    return -1
```

#### Recursive
```python
def binarysearch(arr, target, l, r):
    if l > r:  # left and right ptrs cannot cross
        return -1

    mid = (l+r) // 2

    if arr[mid] == target:
        return mid # target found

    elif target > arr[mid]:
        return binarysearch(arr, target, mid + 1, r)  # reduce search range
    elif target < arr[mid]:
        return binarysearch(arr, target, l, mid - 1)  # reduce search range
```