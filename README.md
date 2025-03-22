TEST CDS
================

## CDS test for Sorting methods

- In python

``` python
def selection_sort(arr):
    for i in range(len(arr)):
        min_index = i
        for j in range(i+1, len(arr)):
            if arr[j] < arr[min_index]:
                min_index = j
        arr[i], arr[min_index] = arr[min_index], arr[i]
    return arr
  
mylist = [3, 6, 8, 10, 1, 2, 1]

print(selection_sort(mylist))
```

    ## [1, 1, 2, 3, 6, 8, 10]
