A sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order

- **It is an in-place and stable sorting algorithm**

## Steps

1. Traverse the list and compare each pair of adjacent items
2. If a pair is in the wrong order, swap them
3. After one complete pass, the largest item is at the end
4. Repeat the process for the remaining items, reducing the number of comparisons after each pass

## Time complexity

| Case             | Complexity | Description                                                               |
| :--------------- | :--------- | :------------------------------------------------------------------------ |
| **Best Case**    | `O(n)`     | The list is already sorted, and the optimized version makes only one pass |
| **Worst Case**   | `O(n²)`    | The list is in reverse order                                              |
| **Average Case** | `O(n²)`    | The list is in a random or jumbled order                                  |

## Implementation

### Un-optimised

```python
def bubblesort(arr):
	n = len(arr)

	for i in range(n):
	    for j in range(n-i-1):
	        if arr[j] > arr[j+1]:
	            arr[j+1], arr[j] = arr[j], arr[j+1]

	return arr
```

### Optimised

```python
def bubblesort(arr):
	n = len(arr)

	for i in range(n):
		swapped = False
		for j in range(n-i-1):
	        if arr[j] > arr[j+1]:
	            arr[j+1], arr[j] = arr[j], arr[j+1]
	            swapped = True

		if not swapped:
			break
	return arr
```
