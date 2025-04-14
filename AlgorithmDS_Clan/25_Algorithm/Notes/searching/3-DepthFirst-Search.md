# DEPTH-FIRST SEARCH
## OVERVIEW
Depth-first search (DFS) is an algorithm for traversing or searching tree or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.

## WHY AND WHEN
Depth First Search (DFS) algorithm, from its name "Depth", discovers the unvisited neighbours of the most recently discovered node x through its out edges. If there is no unvisited neighbour from the node x, the algorithm backtracks to discover the unvisited neighbours of the node (through its out edges) from which node x was discovered, and so forth, till all the nodes reachable from the origional source are visited (we can continue and take another origional source if there are remaining unvisited nodes and so forth).

Depth First Search is commonly used when you need to search the entire tree. It's easier to implement (using recursion) than BFS, and requires less state: While BFS requires you store the entire 'frontier', DFS only requires you store the list of parent nodes of the current element.

## PROS AND CONS
Advantages 
DFSconsumes very less memory space.
It will reach at the goal node in a less time period than BFS if it traverses in a right path.
It may find a solution without examining much of search because we may get the desired solution in the very first go.
Disadvantages.
It is possible that may states keep reoccurring. There is no guarantee of finding the goal node. Sometimes the states may also enter into infinite loops.

