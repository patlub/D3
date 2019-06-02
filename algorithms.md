## Algorithms

1. ### Breadth First Search

    Breadth-first search (BFS) is an algorithm for traversing or searching tree or graph data structures. It starts at the tree root , and explores all of the neighbor nodes at the present depth prior to moving on to the nodes at the next depth level.

    #### Time and space complexity
    The time complexity can be expressed as O(|V|+|E|), since every vertex and every edge will be explored in the worst case. |V| is the number of vertices and |E| is the number of edges in the graph. Note that O(|E|) may vary between O(1) and O(|V|^{2}), depending on how sparse the input graph is.

    The space complexity can be expressed as O(|V|), where |V| is the set of vertices. 
    
    #### Code implementation
    
    [https://github.com/patlub/algorithms/blob/cf59c5235df9fdcb72514d73e7cc157e3bca837b/graph.js#L58](https://github.com/patlub/algorithms/blob/cf59c5235df9fdcb72514d73e7cc157e3bca837b/graph.js#L58)
    
2. ### Depth First Search
    
    Depth-first search (DFS) is an algorithm for traversing or searching tree or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.
   

    #### Code implementation
    [https://github.com/patlub/algorithms/blob/cf59c5235df9fdcb72514d73e7cc157e3bca837b/graph.js#L81](https://github.com/patlub/algorithms/blob/cf59c5235df9fdcb72514d73e7cc157e3bca837b/graph.js#L81)
    
    Time complexity is O(V + E)
    
3. ### Sorting
    I have Implemented binary search, bubblesort, insertion sort, linear sort, heap sort, merge sort, quick sort, selection sort, shellsort algorithms - [here](https://github.com/patlub/algorithms)    
    
4. ### A* Search
    A* is an informed search algorithm, or a best-first search, meaning that it is formulated in terms of weighted graphs: starting from a specific starting node of a graph, it aims to find a path to the given goal node having the smallest cost (least distance travelled, shortest time, etc.). It does this by maintaining a tree of paths originating at the start node and extending those paths one edge at a time until its termination criterion is satisfied.

    At each iteration of its main loop, A* needs to determine which of its paths to extend. It does so based on the cost of the path and an estimate of the cost required to extend the path all the way to the goal
    
    ```
    
    push startNode onto openList
    while(openList is not empty) {
     currentNode = find lowest f in openList
     if currentNode is final, return the successful path
     push currentNode onto closedList and remove from openList
     foreach neighbor of currentNode {
         if neighbor is not in openList {
                save g, h, and f then save the current parent
                add neighbor to openList
         }
         if neighbor is in openList but the current g is better than previous g {
                 save g and f, then save the current parent
         }
     }

    ```
    
5. ### Hashing    
    A hashing algorithm is a cryptographic hash function. It is a mathematical algorithm that maps data of arbitrary size to a hash of a fixed size. It’s designed to be a one-way function, infeasible to invert. However, nowadays several hashing algorithms are being compromised. This happened to MD5, for example — a widely known hash function designed to be a cryptographic hash function, which is now so easy to reverse — that we could only use for verifying data against unintentional corruption.

    Characteristics of a good cryptographic hash function are:
    
        1. It should be fast to compute the hash value for any kind of data
        2. It should be impossible to regenerate a message from its hash value (brute force attack as the only option)
        3. It should avoid hash collisions, each message has its own hash.
        4. Every change to a message, even the smallest one, should change the hash value. It should be completely different. It’s called the avalanche effect
        
    Popular hashing algorithms are:

        * MD5
        * SHA-1
        * SHA-2
        * SHA-3
        
