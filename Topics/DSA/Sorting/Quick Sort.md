A "divide and conquer" sorting algorithm

## Steps

### Quick Sort

1. Choose an element from the array as the pivot
2. Rearrange (partition) the elements of the array so that:  
   • All elements less than the pivot appear to its left
   • All elements greater than the pivot appear to its right
3. Recursively apply the same process to the left and right sub-arrays
### Partition

1. Choose the first element as the pivot
2. Set two markers:
   • `l` pointer pointing to the element just after the pivot  
   • `r` pointer pointing to the last element of the array
3. Repeat the following:  
   • Move `l` right while the `arr[l] <= pivot`
   • Move `r` left while the `arr[r] > pivot`
   • If `l <= r`, swap the elements at these positions
4. When `l > r`, swap the pivot with the element at `r`
5. Return `r`, which is the index where the pivot is now correctly placed

## Time complexity
| Case             | Complexity   | Description                                                                                                                   |
| :--------------- | :----------- | :---------------------------------------------------------------------------------------------------------------------------- |
| **Best Case**    | `O(n log n)` | The pivot always divides the list into two nearly equal halves                                                                |
| **Worst Case**   | `O(n²)`      | The pivot is consistently the smallest or largest element, leading to unbalanced partitions (e.g., on an already sorted list) |
| **Average Case** | `O(n log n)` | The pivot choices lead to reasonably balanced partitions                                                                      |

## Implementation

```python
def quicksort(arr, low, high):
    if low < high:
        pivot = partition(arr, low, high)
        quicksort(arr, pivot + 1, high)
        quicksort(arr, low, pivot - 1)

    return arr


def partition(arr, low, high):
    pivot = arr[low]
    l = low + 1
    r = high

    while l <= r:
        while l <= r and arr[l] <= pivot:
            l += 1
        while l <= r and arr[r] > pivot:
            r -= 1

        if l <= r:
            arr[l], arr[r] = arr[r], arr[l]

    arr[r], arr[low] = arr[low], arr[r]

    return r
```
