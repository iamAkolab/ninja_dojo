# BREADTH FIRST SEARCH
## OVERVIEW
Breadth-first search (BFS) is an algorithm for searching a tree data structure for a node that satisfies a given property. It starts at the tree root and explores all nodes at the present depth prior to moving on to the nodes at the next depth level

## WHY AND WHEN
Breadth First Search (BFS) algorithm, from its name "Breadth", discovers all the neighbours of a node through the out edges of the node then it discovers the unvisited neighbours of the previously mentioned neighbours through their out edges and so forth, till all the nodes reachable from the origional source are visited (we can continue and take another origional source if there are remaining unvisited nodes and so forth). That's why it can be used to find the shortest path (if there is any) from a node (origional source) to another node if the weights of the edges are uniform.

Breadth First Search is generally the best approach when the depth of the tree can vary, and you only need to search part of the tree for a solution. For example, finding the shortest path from a starting value to a final value is a good place to use BFS.

## PROS AND CONS
Advantages 
It does not follow a single unfruitful path for a long time. It finds the minimal solution in case of multiple paths.

Disadvantages.
BFS consumes large memory space. Its time complexity is more.
It has long pathways, when all paths to a destination are on approximately the same search depth.

![Alt Text](https://github.com/iamAkolab/ninja_dojo/blob/main/AlgorithmDS_Clan/25_Algorithm/img/Breadth-First%20Search.jpg)
## STEPS
The algorithm works as follows:

* Step 1 - Start by putting any one of the graph's vertices at the back of a queue.
* Step 2 - Take the front item of the queue and add it to the visited list.
* Step 3 - Create a list of that vertex's adjacent nodes. Add the ones which aren't in the visited list to the back of the queue.
* Step 4 - Keep repeating steps 2 and 3 until the queue is empty.

## CODE IMPLEMENTATION
```
# BFS algorithm in Python

import collections


# BFS algorithm
def bfs(graph, root):

    visited, queue = set(), collections.deque([root])
    visited.add(root)

    while queue:

        # Dequeue a vertex from queue
        vertex = queue.popleft()
        print(str(vertex) + " ", end="")


        # If not visited, mark it as visited, and
        # enqueue it
        for neighbour in graph[vertex]:
            if neighbour not in visited:
                visited.add(neighbour)
                queue.append(neighbour)

if __name__ == '__main__':
    graph = {0: [1, 2], 1: [2], 2: [3], 3: [1, 2]}
    print("Following is Breadth First Traversal: ")
    bfs(graph, 0)

```




```
# Python3 Program to print BFS traversal
# from a given source vertex. BFS(int s)
# traverses vertices reachable from s.
from collections import defaultdict
 
# This class represents a directed graph
# using adjacency list representation
class Graph:
 
    # Constructor
    def __init__(self):
 
        # default dictionary to store graph
        self.graph = defaultdict(list)
 
    # function to add an edge to graph
    def addEdge(self,u,v):
        self.graph[u].append(v)
 
    # Function to print a BFS of graph
    def BFS(self, s):
 
        # Mark all the vertices as not visited
        visited = [False] * (max(self.graph) + 1)
 
        # Create a queue for BFS
        queue = []
 
        # Mark the source node as
        # visited and enqueue it
        queue.append(s)
        visited[s] = True
 
        while queue:
 
            # Dequeue a vertex from
            # queue and print it
            s = queue.pop(0)
            print (s, end = " ")
 
            # Get all adjacent vertices of the
            # dequeued vertex s. If a adjacent
            # has not been visited, then mark it
            # visited and enqueue it
            for i in self.graph[s]:
                if visited[i] == False:
                    queue.append(i)
                    visited[i] = True
 
# Driver code
 
# Create a graph given in
# the above diagram
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)
 
print ("Following is Breadth First Traversal"
                  " (starting from vertex 2)")
g.BFS(2)
 
# This code is contributed by Neelam Yadav
```  

## BIG O ANALYSIS
* Class:	Search algorithm
* Time complexity: O(V + E), where V is the number of vertices and E is the number of edges in the graph.
* Space complexity: O(|V|) = O(b^d)

## BFS Algorithm Applications
* To build index by search index
* For GPS navigation
* Path finding algorithms
* In Ford-Fulkerson algorithm to find maximum flow in a network
* Cycle detection in an undirected graph
* In minimum spanning tree
