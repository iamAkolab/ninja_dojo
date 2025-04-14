# INSERTION SORT
## OVERVIEW
Insertion Sort is a sorting algorithm that places an unsorted element at its suitable place in each iteration.

## WHY AND WHEN
Insertion sort works similarly as we sort cards in our hands in a card game. We assume that the first card is already sorted then, we select an unsorted card. If the unsorted card is greater than the card in hand, it is placed on the right otherwise, to the left. In the same way, other unsorted cards are taken and put in their right place.

## PROS AND CONS
Advantages 
Simple implementation: Jon Bentley shows a three-line C version, and a five-line optimized version[1]
Efficient for (quite) small data sets, much like other quadratic sorting algorithms
More efficient in practice than most other simple quadratic (i.e., O(n2)) algorithms such as selection sort or bubble sort
Adaptive, i.e., efficient for data sets that are already substantially sorted: the time complexity is O(kn) when each element in the input is no more than k places away from its sorted position
Stable; i.e., does not change the relative order of elements with equal keys
In-place; i.e., only requires a constant amount O(1) of additional memory space
Online; i.e., can sort a list as it receives it.

Disadvantages.
it does not perform as well as other, better sorting algorithms. With n-squared steps required for every n element to be sorted, the insertion sort does not deal well with a huge list

## STEPS
The algorithm works as follows:

Step 1 − If it is the first element, it is already sorted. return 1;
Step 2 − Pick the next element
Step 3 − Compare with all elements in the sorted sub-list
Step 4 − Shift all the elements in the sorted sub-list that is greater than the value to be sorted
Step 5 − Insert the value
Step 6 − Repeat until the list is sorted

##CODE IMPLEMENTATION
```
# Insertion sort in Python

def insertionSort(array):


    for step in range(1, len(array)):
        key = array[step]
        j = step - 1
        
        # Compare key with each element on the left of it until an element smaller than it is found
        # For descending order, change key<array[j] to key>array[j].        
        while j >= 0 and key < array[j]:
            array[j + 1] = array[j]
            j = j - 1
        
        # Place key at after the element just smaller than it.
        array[j + 1] = key
```

```
data = [9, 5, 1, 4, 3]
insertionSort(data)
print('Sorted Array in Ascending Order:')
print(data)
```


## BIG O ANALYSIS
* Class:	Sorting algorithm
* Time Complexity:	 
* Best	O(n)
* Worst	O(n2)
* Average	O(n2)
* Space Complexity:	O(1)
* Stability     Yes 
