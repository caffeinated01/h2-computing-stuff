A simple sorting algorithm that builds the final sorted list one item at a time

- **It is an in-place and stable sorting algorithm**

## Steps

1. Start by considering the first element as the sorted subarray, and the rest as unsorted.
2. For each iteration, take the first element of the unsorted subarray (from i=1)
3. Move backward through the sorted subarray, comparing and shifting elements to the  
   right until the correct position for the current element is found.
4. Insert the element into its correct position.
5. Repeat until all elements have been inserted into the sorted subarray

> [!note] Each iteration increases the size of the sorted subarray by one element and decreases the size of the unsorted subarray by one.

## Time Complexity

| Case             | Complexity | Description                                                           |
| :--------------- | :--------- | :-------------------------------------------------------------------- |
| **Best Case**    | `O(n)`     | The list is already sorted, requiring only one comparison per element |
| **Worst Case**   | `O(n²)`    | The list is in reverse order, requiring maximum shifting              |
| **Average Case** | `O(n²)`    | The list is in a random or jumbled order                              |

## Implementation

```python
def insertionsort(arr):
    for i in range(1, len(arr)):
        key = arr[i] # the element to be inserted
        # move elements of arr[0..i-1] that are greater than key,
        # to one position ahead of their current position
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1

        arr[j + 1] = key
    return arr
```
