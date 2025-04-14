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

![Alt text](https://github.com/iamAkolab/ninja_dojo/blob/main/AlgorithmDS_Clan/25_Algorithm/img/Depth%20First%20Search.jpg)

## STEPS
Rule 1 − Visit the adjacent unvisited vertex. Mark it as visited. Display it. Push it in a stack.
Rule 2 − If no adjacent vertex is found, pop up a vertex from the stack. (It will pop up all the vertices from the stack, which do not have adjacent vertices.)
Rule 3 − Repeat Rule 1 and Rule 2 until the stack is empty.

The algorithm works as follows:
Step 1 - Start by putting any one of the graph's vertices on top of a stack.
Step 2 - Take the top item of the stack and add it to the visited list.
Step 3 - Create a list of that vertex's adjacent nodes. Add the ones which aren't in the visited list to the top of the stack.
Step 4 - Keep repeating steps 2 and 3 until the stack is empty.

## CODE IMPLEMENTATION
### DFS algorithm in Python

```
# DFS algorithm
def dfs(graph, start, visited=None):
    if visited is None:
        visited = set()
    visited.add(start)

    print(start)

    for next in graph[start] - visited:
        dfs(graph, next, visited)
    return visited

graph = {'0': set(['1', '2']),
         '1': set(['0', '3', '4']),
         '2': set(['0']),
         '3': set(['1']),
         '4': set(['2', '3'])}


dfs(graph, '0')
```

```
# Python3 program to print DFS traversal
# from a given given graph
from collections import defaultdict
  
# This class represents a directed graph using
# adjacency list representation
  
  
class Graph:
  
    # Constructor
    def __init__(self):
  
        # default dictionary to store graph
        self.graph = defaultdict(list)
  
    # function to add an edge to graph
    def addEdge(self, u, v):
        self.graph[u].append(v)
  
    # A function used by DFS
    def DFSUtil(self, v, visited):
  
        # Mark the current node as visited
        # and print it
        visited.add(v)
        print(v, end=' ')
  
        # Recur for all the vertices
        # adjacent to this vertex
        for neighbour in self.graph[v]:
            if neighbour not in visited:
                self.DFSUtil(neighbour, visited)
  
    # The function to do DFS traversal. It uses
    # recursive DFSUtil()
    def DFS(self, v):
  
        # Create a set to store visited vertices
        visited = set()
  
        # Call the recursive helper function
        # to print DFS traversal
        self.DFSUtil(v, visited)
  
# Driver code
# Create a graph given
# in the above diagram
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)
  
print("Following is DFS from (starting from vertex 2)")
g.DFS(2)
```

## BIG O ANALYSIS
* Class:	Search algorithm
* Time complexity: O(V + E), where V is the number of vertices and E is the number of edges in the graph.
* Space Complexity: O(V), Since an extra visited array is needed of size V

## Application of DFS Algorithm
* For finding the path
* To test if the graph is bipartite
* For finding the strongly connected components of a graph
* For detecting cycles in a graph
