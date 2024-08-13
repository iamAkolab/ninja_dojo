# LINEAR SEARCH
## OVERVIEW
Linear search or Sequential search is a method for finding an element within a list. It sequentially checks each element of the list until a match is found or the whole list has been searched

## WHY AND WHEN
Linear search is usually very simple to implement and is practical when the list has only a few elements, or when performing a single search in an unordered list.

When many values have to be searched in the same list, it often pays to pre-process the list in order to use a faster method. For example, one may sort the list and use binary search, or build an efficient search data structure from it. Should the content of the list change frequently, repeated re-organization may be more trouble than it is worth.

In practice, even on medium-sized arrays (around 100 items or less), it might be infeasible to use anything else. On larger arrays, it only makes sense to use other, faster search methods if the data is large enough because the initial time to prepare (sort) the data is comparable to many linear searches.


## PROS AND CONS
Advantages 
When a key element matches the first element in the array, then the linear search algorithm is the best case because executing time of the linear search algorithm is 0 (n), where n is the number of elements in an array.
Disadvantages.
Inversely, when a key element matches the last element in the array or a key element doesn't match any element then the Linear search algorithm is a worst-case.

## STEPS
Linear Search ( Array A, Value x)  Step 1: Set i to 1
Step 2: if i > n then go to step 7
Step 3: if A[i] = x then go to step 6
Step 4: Set i to i + 1
Step 5: Go to Step 2
Step 6: Print Element x Found at index i and go to step 8
Step 7: Print element not found		Step 8: Exit

## PSEUDO-CODE
```
procedure linear_search (list, value)


   for each item in the list
      if match item == value
         return the item's location
      end if
   end for


end procedure
```
## CODE IMPLEMENTATION
Python3 code to linearly search x in arr[].
If x is present then return its location,
otherwise return -1
 
``` 
def search(arr, n, x):
 
    for i in range(0, n):
        if (arr[i] == x):
            return i
    return -1

 
-- Driver Code
arr = [2, 3, 4, 10, 40]
x = 10
n = len(arr)
 
# Function call
result = search(arr, n, x)
if(result == -1):
    print("Element is not present in array")
else:
    print("Element is present at index", result)
```

## BIG O ANALYSIS
Class:	Search algorithm
Worst-case performance:	O(n)
Best-case performance:	O(1)
Average performance:	O(n/2)
Worst-case space complexity:	O(1) iterative
