# BINARY SEARCH
## OVERVIEW
Binary search or half-interval search or logarithmic search is a search algorithm that finds the position of a target value within a sorted array. Binary search is an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing in half the portion of the list that could contain the item until you've narrowed down the possible locations to just one

## WHY AND WHEN
Binary search is known for being an O(log n) which means that the time complexity of our operation is proportional to the logarithm of its input size.

In this example, with a list of 12 elements, we only made 3 operations to return the desired element, that’s very impressive and very efficient. Iterating all over the list just to return a specific element, in this example, we would make at least 8 operations

## PROS AND CONS
Advantages 
When a key element matches the middle element in the array, then the Binary search algorithm is the best case because the execution time of the Binary search algorithm is 0 (log n), where n is the number of elements in an array.
Disadvantages.
When a key element matches the first or last element in the array, then the Binary search algorithm is the best case because the execution time of the Binary search algorithm is 0 (log n), where n is the number of elements in an array.

![alt_text](https://github.com/iamAkolab/ninja_dojo/blob/main/AlgorithmDS_Clan/25_Algorithm/img/Binary%20Search.jpg)

## STEPS
Step 1 - Read the search element from the user.
Step 2 - Find the middle element in the sorted list.
Step 3 - Compare the search element with the middle element in the sorted list.
Step 4 - If both are matched, then display "Given element is found!!!" and terminate the function.
Step 5 - If both are not matched, then check whether the search element is smaller or larger than the middle element.
Step 6 - If the search element is smaller than the middle element, repeat steps 2, 3, 4 and 5 for the left sublist of the middle element.
Step 7 - If the search element is larger than the middle element, repeat steps 2, 3, 4 and 5 for the right sublist of the middle element.
Step 8 - Repeat the same process until we find the search element in the list or until the sublist contains only one element.
Step 9 - If that element also doesn't match with the search element, then display "Element is not found in the list!!!" and terminate the function.

## PSEUDO-CODE
```
Procedure binary_search
   A ← sorted array
   n ← size of array
   x ← value to be searched


   Set lowerBound = 1
   Set upperBound = n 


   while x not found
      if upperBound < lowerBound 
         EXIT: x does not exists.
   
      set midPoint = lowerBound + ( upperBound - lowerBound ) / 2
      
      if A[midPoint] < x
         set lowerBound = midPoint + 1
         
      if A[midPoint] > x
         set upperBound = midPoint - 1 


      if A[midPoint] = x 
         EXIT: x found at location midPoint
   end while
end procedure
```

## CODE IMPLEMENTATION
* Python3 code to implement iterative Binary Search.
 
* It returns location of x in given array arr
* if present, else returns -1

```
def binarySearch(arr, l, r, x):
 
    while l <= r:
 
        mid = l + (r - l) // 2;
         
        # Check if x is present at mid
        if arr[mid] == x:
            return mid
 
        # If x is greater, ignore left half
        elif arr[mid] < x:
            l = mid + 1
 
        # If x is smaller, ignore right half
        else:
            r = mid - 1
     
    # If we reach here, then the element
    # was not present
    return -1
```
 
## Driver Code
```
arr = [ 2, 3, 4, 10, 40 ]
x = 10
```

## Function call
```
result = binarySearch(arr, 0, len(arr)-1, x)
 
if result != -1:
    print ("Element is present at index % d" % result)
else:
    print ("Element is not present in array")
```

## BIG O ANALYSIS
* Class:	Search algorithm
* Worst-case performance:	O(n)
* Best-case performance:	O(1)
* Average performance:	O(n/2)
* Worst-case space complexity:	O(1) iterative
