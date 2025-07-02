An efficient, stable, "divide and conquer" sorting algorithm

## Steps
### Divide Phase:
- The list is split into two halves.
- Each half is split again and again, until you end up with many small lists that each
have only one item.
- A list with one item is already sorted
### Conquer (Merge) Phase:
- Now, you start combining the small lists back together.
- As you merge, you compare the items from each list and place them in the right order.
- You keep merging until all the little lists become one big sorted list.

## Time Complexity
| Case             | Complexity   | Description                                                                                                                                                                             |
| :--------------- | :----------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Best Case**    | `O(n log n)` | The average time complexity is O(n log n), as the algorithm recursively splits the array into halves ($\log_2n$ levels), and each level performs a linear-time merge of all n elements. |
| **Worst Case**   | `O(n log n)` | The performance is consistent regardless of initial order                                                                                                                               |
| **Average Case** | `O(n log n)` | The performance is consistent regardless of initial order                                                                                                                               |

## Implementation (Python)
```python
def mergesort(arr):
    n = len(arr)

    if n == 1:
        return arr

    mid = n // 2

    left = mergesort(arr[:mid])
    right = mergesort(arr[mid:])

    return merge(left, right)


def merge(left, right):
    out = []
    i = j = 0

    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            out.append(left[i])
            i += 1

        else:
            out.append(right[j])
            j += 1

    out.extend(left[i:])
    out.extend(right[j:])

    return out
```
