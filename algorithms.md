## Algorithms

1. ### Breadth First Search

    Breadth-first search (BFS) is an algorithm for traversing or searching tree or graph data structures. It starts at the tree root , and explores all of the neighbor nodes at the present depth prior to moving on to the nodes at the next depth level.

    #### Time and space complexity
    The time complexity can be expressed as O(|V|+|E|), since every vertex and every edge will be explored in the worst case. |V| is the number of vertices and |E| is the number of edges in the graph. Note that O(|E|) may vary between O(1) and O(|V|^{2}), depending on how sparse the input graph is.

    When the number of vertices in the graph is known ahead of time, and additional data structures are used to determine which vertices have already been added to the queue, the space complexity can be expressed as O(|V|), where |V| is the cardinality of the set of vertices. This is in addition to the space required for the graph itself, which may vary depending on the graph representation used by an implementation of the algorithm.
    
    #### Pseudocode
    ```
    procedure BFS(G,start_v):
      let S be a queue
      S.enqueue(start_v)
      while S is not empty
          v = S.dequeue()
          if v is the goal:
              return v
          for all edges from v to w in G.adjacentEdges(v) do
              if w is not labeled as discovered:
                 label w as discovered
                 w.parent = v
                 S.enqueue(w)
    ```
    
2. ### Depth First Search
    
    Depth-first search (DFS) is an algorithm for traversing or searching tree or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.
    
    
    This recursive nature of DFS can be implemented using stacks. The basic idea is as follows:
Pick a starting node and push all its adjacent nodes into a stack.
Pop a node from stack to select the next node to visit and push all its adjacent nodes into a stack.
Repeat this process until the stack is empty. However, ensure that the nodes that are visited are marked. This will prevent you from visiting the same node more than once. If you do not mark the nodes that are visited and you visit the same node more than once, you may end up in an infinite loop.

    #### Pseudocode
    ```
    DFS-iterative (G, s):                                   //Where G is graph and s is source vertex
      let S be stack
      S.push( s )            //Inserting s in stack 
      mark s as visited.
      while ( S is not empty):
          //Pop a vertex from stack to visit next
          v  =  S.top( )
         S.pop( )
         //Push all the neighbours of v in stack that are not visited   
        for all neighbours w of v in Graph G:
            if w is not visited :
                     S.push( w )         
                    mark w as visited


    DFS-recursive(G, s):
        mark s as visited
        for all neighbours w of s in Graph G:
            if w is not visited:
                DFS-recursive(G, w)
    ```
    
    Time complexity is O(V + E), when implemented using an adjacency list.
    
3. ### A* Search
    A* is an informed search algorithm, or a best-first search, meaning that it is formulated in terms of weighted graphs: starting from a specific starting node of a graph, it aims to find a path to the given goal node having the smallest cost (least distance travelled, shortest time, etc.). It does this by maintaining a tree of paths originating at the start node and extending those paths one edge at a time until its termination criterion is satisfied.

    At each iteration of its main loop, A* needs to determine which of its paths to extend. It does so based on the cost of the path and an estimate of the cost required to extend the path all the way to the goal
    
    
3. ### Hashing    
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
        
3. ### Sorting
Implementation of binary search, bubblesort, insertion sort, linear sort, merge sort, quick sort, selection sort, shellsort algorithms - [here](https://github.com/patlub/algorithms)
