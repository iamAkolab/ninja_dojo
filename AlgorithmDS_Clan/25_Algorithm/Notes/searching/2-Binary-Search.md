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
