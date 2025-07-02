A sequential search algorithm that starts from the beginning and checks every element of a list one by one until a match is found or the whole list has been searched

### Time Complexity

| Case             | Complexity | Description                                                   |
| :--------------- | :--------- | :------------------------------------------------------------ |
| **Best Case**    | `O(1)`     | The target item is the first element checked                  |
| **Worst Case**   | `O(n)`     | The target item is the last element, or it is not in the list |
| **Average Case** | `O(n)`     | On average, the algorithm checks n/2 elements                 |

### Implementation

#### Iterative

```python
def linearsearch(arr, target):
    for idx, val in enumerate(arr):
        if val == target:
            return idx  # target found
    return -1 # target not found
```

#### Recursive

```python
def linearsearch(arr, target, idx=0):
    if idx >= len(arr):
        return -1 # target not found

    if arr[idx] == target:
        return idx # target found

    return linearsearch(arr, target, idx+1)
```
