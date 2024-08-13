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
