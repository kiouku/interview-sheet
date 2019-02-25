# Must know algorithms

## Comparison based sort

### 1. Bubble Sort

#### Definition

* It iterates left to right comparing every couple, moving the smaller element to the left.
* It repeats this process until it no longer moves and element to the left.

#### What you need to know

* While it is very simple to implement, it is the least efficient of the sorting methods.
* Know that it moves one space to the right comparing two elements at a time and moving the smaller on to left.
* Can be optimized to avoid up to 50% of the comparisons by starting from the last swap in the previous iteration.
* Stable.

#### Big O efficiency

Best Case Sort: O(n)
Average Case Sort: O(n^2)
Worst Case Sort: O(n^2)
Space: O(1)

### 2. Insertion Sort

#### Definition

* Builds the final sorted array (or list) one item at a time.
* At each iteration, insertion sort removes one element from the input data, finds the location it belongs within the sorted list, and inserts it there. It repeats until no input elements remain.

#### What you need to know

* Efficient for (quite) small data sets, much like other quadratic sorting algorithms such as selection sort or bubble sort
* More efficient in practice than most other simple quadratic algorithms.
* Stable

#### Big O efficiency

Best Case Sort: O(n^2)
Average Case Sort: O(n^2)
Worst Case Sort: O(n^2)
Space: O(1)

### 3. Selection Sort

#### Definition

* The algorithm divides the input list into two parts: the sublist of items already sorted, which is built up from left to right at the front (left) of the list, and the sublist of items remaining to be sorted that occupy the rest of the list.
* Initially, the sorted sublist is empty and the unsorted sublist is the entire input list.
* The algorithm proceeds by finding the smallest (or largest, depending on sorting order) element in the unsorted sublist, exchanging (swapping) it with the leftmost unsorted element (putting it in sorted order), and moving the sublist boundaries one element to the right

#### What you need to know

* Generally performs worse than the similar insertion sort.
* Selection sort is noted for its simplicity, and it has performance advantages over more complicated algorithms in certain situations, particularly where auxiliary memory is limited.
* Unstable. Stable implementation can be done with additional data structure.

#### Big O efficiency

Best Case Sort: O(n^2)
Average Case Sort: O(n^2)
Worst Case Sort: O(n^2)
Space: O(1)

### 4. Merge Sort

#### Definition

* Divide the unsorted list into n sublists, each containing 1 element (a list of 1 element is considered sorted).
* Repeatedly merge sublists to produce new sorted sublists until there is only 1 sublist remaining. This will be the sorted list.

#### What you need to know

* Implementation of the divide and conquer algorithm stategy.
* Know that it divides all the data into as small possible sets then compares them.
* For most of the implementations is a stable sort.

#### Big O efficiency

Best Case Sort: O(n)
Average Case Sort: O(n log n)
Worst Case Sort: O(n log n)

### 5. Quicksort

#### Definition

* Pick an element, called a pivot, from the array.
* Partitioning: reorder the array so that all elements with values less than the pivot come before the pivot, while all elements with values greater than the pivot come after it (equal values can go either way). After this partitioning, the pivot is in its final position. This is called the partition operation.
* Recursively apply the above steps to the sub-array of elements with smaller values and separately to the sub-array of elements with greater values.

#### What you need to know

* While it has the same Big O as (or worse in some cases) many other sorting algorithms it is often faster in practice than many other sorting algorithms, such as merge sort.
* Know that it halves the data set by the average continuously until all the information is sorted.
* Unstable.

#### Big O efficiency

Best Case Sort: O(n)
Average Case Sort: O(n log n)
Worst Case Sort: O(n^2)

### 6. Heap Sort

#### Definition

* In the first step, a heap is built out of the data. The heap is often placed in an array with the layout of a complete binary tree. The complete binary tree maps the binary tree structure into the array indices; each array index represents a node; the index of the node's parent, left child branch, or right child branch are simple expressions. For a zero-based array, the root node is stored at index 0; if i is the index of the current node, then.
* In the second step, a sorted array is created by repeatedly removing the largest element from the heap (the root of the heap), and inserting it into the array. The heap is updated after each removal to maintain the heap property. Once all objects have been removed from the heap, the result is a sorted array.
* Parent(i) = floor((i-1) / 2) where floor functions map a real number to the smallest leading integer. iLeftChild(i) = 2*i + 1 iRightChild(i) = 2*i + 2

#### What you need to know

* Heapsort can be thought of as an improved selection sort.
* Although somewhat slower in practice on most machines than a well-implemented quicksort, it has the advantage of a more favorable worst-case O(n log n) runtime.
* Not a stable sort.

#### Big O efficiency

Best Case Sort: O(n log n) O(n) if equal keys
Average Case Sort: O(n log n)
Worst Case Sort: O(n log n)
Space: O(1)

## Merge Sort vs Quicksort

* Quicksort is likely faster in practice.
* Merge Sort divides the set into the smallest possible groups immediately then reconstructs the incrementally as it sorts the groupings.
* Quicksort continually divides the set by the average, until the set is recursively sorted.

## Merge Sort vs Heapsort

* Merge sort requires O(n) auxiliary space, but heapsort requires only a constant amount. Heapsort typically runs faster in practice on machines with small or slow data caches, and does not require as much external memory.
* Merge sort on arrays has considerably better data cache performance, often outperforming heapsort on modern desktop computers because merge sort frequently accesses contiguous memory locations (good locality of reference); heapsort references are spread throughout the heap.
* Heapsort is not a stable sort; merge sort is stable.
* Merge sort parallelizes well and can achieve close to linear speedup with a trivial implementation; heapsort is not an obvious candidate for a parallel algorithm.
* Merge sort can be adapted to operate on singly linked lists with O(1) extra space. Heapsort can be adapted to operate on doubly linked lists with only O(1) extra space overhead.
* Merge sort is used in external sorting; heapsort is not. Locality of reference is the issue.

## Non comparison sort algorithms

### Pigeonhole Sort

#### Definition

* Given an array of values to be sorted, set up an auxiliary array of initially empty "pigeonholes," one pigeonhole for each key through the range of the original array.
* Going over the original array, put each value into the pigeonhole corresponding to its key, such that each pigeonhole eventually contains a list of all values with that key.
* Iterate over the pigeonhole array in order, and put elements from non-empty pigeonholes back into the original array.

#### What you need to know

* Suitable for sorting lists of elements where the number of elements (n) and the length of the range of possible key values (N) are approximately the same.
* Stable.

#### Big O efficiency

Worst Case Sort: O(N+n) where N is the range of key values and n is the input size
Space: O(N+n)

### 1. Breadth First Search

#### Definition

An algorithm that searches a tree (or graph) by searching levels of the tree first, starting at the root.

* It finds every node on the same level, most often moving left to right.
* While doing this it tracks the children nodes of the nodes on the current level.

#### What you need to know

* It can be used to computed shortest path to every node in graph with edges of weight 1.
* It can be used to detect cycles in a graph.
* Optimal for searching a tree that is wider than it is deep.
* Uses a queue to store information about the tree while it traverses a tree.
* The queue uses more memory because it needs to stores pointers.

#### Big O efficiency

O(|E| + |V|)

### 2. Depth First Search

#### Definition

An algorithm that searches a tree (or graph) by searching depth of the tree first, starting at the root.

* It traverses left down a tree until it cannot go further.
* Once it reaches the end of a branch it traverses back up trying the right child of nodes on that branch, and if possible left from the right children.
* When finished examining a branch it moves to the node right of the root then tries to go left on all it&rsquo;s children until it reaches the bottom.
* The right most node is evaluated last (the node that is right of all it&rsquo;s ancestors).

#### What you need to know:

* Optimal for searching a tree that is deeper than it is wide.
* Uses a stack to push nodes onto.
* Because a stack is LIFO it does not need to keep track of the nodes pointers and is therefore less memory intensive than breadth first search.
* It can be used to detect cycles in a graph, compute strong connected components and topological order.

#### Big O efficiency

O(|E| + |V|)

## Breadth First Search Vs. Depth First Search

* The simple answer to this question is that it depends on the size and shape of the tree.
* For wide, shallow trees use Breadth First Search
* For deep, narrow trees use Depth First Search

#### Nuances

* Because BFS uses queues to store information about the nodes and its children, it could use more memory than is available on your computer. (But you probably won&rsquo;t have to worry about this.)
* If using a DFS on a tree that is very deep you might go unnecessarily deep in the search. See <a href="http://xkcd.com/761/">xkcd</a> for more information.

### 3. Dijkstra's algorithm. Computing the shortest path problem

#### Definition

Traveses the graph as breadth search with the peculiarity of applying Dijstra greedy criteria to select the next node to be procesed. Dijkstra Greedy criterion is the sum of the shortest path until the previous node plus the weight of the edge that connects to the still unvisited node.

#### What you need to know:

* It works in any directed graph with non-negative edge lengths
* It computes the shortest paths from a source vertex to all other vertices.
* It can be optimized to linear time by using a heap where each vertex not visited connected to a vertex already visited is stored using as key the Dijkstra greedy criteria for that node.

#### Big O efficiency

* Naive implementation O(n * m)
* With heap O(m * log n)

### 3. Prim's algorithm. Computing the Minimum Spanning Tree problem

#### Definition

Greedy algorithm that starts from any node. Among all the edges between the already visited nodes and the non visited we select the one with smallest weight. The algorigthm stops when the number of visited nodes is the same as the number of nodes in the graph.

#### What you need to know:

* It works only with undirected graphs.
* If the given graph is not strongly connected, several iterations of the algorithm computing the MST of each connected component of the graph.
* Applicacions: network, clustering.

#### Big O efficiency

* Assume adjacency list in the graph.
* Naive implementation O(|E| * |V|)
* With heap O(|E| * log|V|)

### 4. Kruskal's algorithm. Computing the Minimum Spanning Tree problem

#### Definition

Greedy algorithm that starts by sorting all the edges by weigh. For every edge select the next one that does not introduce a cycle

Note that as oppose to Prim's it can start from any node and instead of growing the MST from adjacent nodes it will grow several graph components that will concur in the MSRT.

#### What you need to know:

* It can be speed up by using union-find data structure instead of perfoming Depth first or breadth first search to detect nodes that might create a cycle in the MST.
* It works only with undirected graphs.
* If the given graph is not strongly connected, several iterations of the algorithm computing the MST of each connected component of the graph.
* Applicacions: network design, clustering, can be used to approximately solve the traveling salesman problem.

#### Big O efficiency

* Naive implementation O(|E| * |V|) - Iterate on each edge (E) and detect cycle (V)
* With Union-Find O(|E| * log|V|) - Sorting

### 5. Single-link Clustering algorithm. Dividing data in groups

#### Definition

Given n points (Webpages, images, genome fragments...) we want to classify them into coherent k groups.

There a function that provides a similarity measurement between each point belonging to diferent clusters. Thing that have similar distance should be group together. Things that have different distance should be kept separated.

Greedy algorithm that Initially each point is classified into a different cluster. Until the desireed number of clusters is reached the closest pair of points not beloging to the same cluster are taken and merged among their corresponding clusters.

#### What you need to know:

* Exactly as Kruskal's but finishing before.

#### Big O efficiency

* Naive implementation O(|E| * |V|) - Iterate on each edge (E) and detect cycle (V)
* With Union-Find O(|E| * log|V|) - Sorting

### 6. Kosaraju's algorithm. Computing strongly connected components in a directed graph

#### Definition

The goal is to compute all the strongly connected components of a directed graph. directed graphs, a graph is said to be strongly connected or diconnected if every vertex is reachable from every other vertex. The algorithm based on DFS.

Two BFS. First one, iterates on backwards (reversing edges) the graph and creates an array of finishing times. The second DFS processes the nodes in decreasing finishing time(can relabel the nodes) and discovers the leaders of all the strongly connected components.

#### What you need to know:

* If the graph has several connected components an external loop has to be used to itearte on all the nodes

#### Big O efficiency

* O(|E| + |V|)

### 7. Topological Order

#### Definition

It is an ordering of the vertices of a directed acyclic graph so that all of the arcs only go forward in the ordering.

Since every acyclic graph has a sink a possible algorithm would be to find that sink,
label it and recurse in the rest of the graph.

Another alternative is to use a DFS. For each node in the graph that is not explored
a DFS is started recursively. A global label is used to mark the nodes when backtracking the DFS.

#### What you need to know:

* If there is cycle there is no topological ordering. As long as there is no cycles, there is topological order.
* Applications: Sequence of tasks while respecting all precedence constraints.

#### Big O efficiency

* O(|E| + |V|)

### 8. Huffmann Algorithm

#### Definition

Given an alphabet of symbols and its weights/probabilities, huffman encoding provides a mecanishm to assign the shortest binary encoding to the symbols in the weight.

It is a greedy algorithm that on each step takes the two symbols with lowest weight, these will be a assigned a common parent node and will be merged. Once there are just two symbols base case is reached and a huffman tree is generated while backtracking generating two nodes with the same parent per level of recursion.

#### What you need to know:

* Myopic decision: element with lowest weight are selected first to be assigned to a deeper depht in the huffman binary tree and hence to have a longer enconding.

#### Big O efficiency

* O(n)

### 9. Weighted Independent Sets in Path Graphs

#### Definition

Given path graph with non negative weights assign to each vertex, find the set of non adjacent vertices with a maximum total weight.

A possibility is to compute all the possible using recursive calls an memoziation to avoid redudant computations. This would be a top down approach.

```ruby
f(idx,acc,weights)
{
    if (idx > weights.length)
        return acc
    s1 = f(idx+1,weights[idx] + acc,weights)
    s2 = f(idx+1,acc,weights)
    return max{s1,s2}
}
```

The recursive search in the space of solutions of this problem can be reformulated bottom-up with a table (dynamic programming) in which first the solutions to smaller subproblem are computed and aggregated to solve the completeproblem.

```ruby
sum[0] = 0
sum[1] = weights[1]
for i in 2...weights.length
    sum[i] = [sum[i-1], sum[i-2] + weights[i]].max 
end
```

Iterating again on the sum result it is possible to compute the actual vertex in the weighted maximum independent set.  

```ruby
@result = []
i = weights.length-1;
until i<1
    if(sum[i-1] > sum[i-2]+weights[i])
        i-=1
    else
        @result.push(i)
        i-=2  
    end
end
```  

#### Big O efficiency

O(n)

### 10. Knacksack problem

#### Definition

Given a knacksack capacity and a list of item weights and their values, the goal is to fill the knacksack maximizing the value.

In case the items can not be split there are two approaches to solve the problem. Either:

* Use a greedy algorithm to select the items with bigger value that fit the knacksack.
* Use a dynamic programming approach in which either we select the element and we advance subtracting its weight to the knacksack capacity or skip it.

#### What you need to know:

* In case the items can be split there is no greedy solution for the knacksack problem.

#### Big O efficiency

O(n*w)

### 11. Optimized Binary Search Tree. A dynamic programming algorithm

#### Definition

Given the frequency in which every node is accessed, the idea is to balance the tree is a way that the most accesed nodes have are in a shallower position.

It is an optimization problem where we want to minize the sum of the probabilities of accessing every node multiplied by its height.

#### What you need to know:

* A Balanced tree can be used to obtain log n heights per node and this is optimal when probabilities are uniform.
* Greedy approach bottom up or top down similar to huffman coding algorithm does not work.

### 12. Sequence alignment. A dynamic programming algorithm

#### Definition

The goal is to compute a similarity measure between two strings taking into account that diffenrent letters in the same position have a penalization in similarity. It is possible to add gaps to both improve their similarity.

A dynamic programing solution is required to solve this problem. First subproblems to be solved have to be idenfied. Then a recurrence is infered from which it will be possible to implement an iterative bottom up approach.

In the base case, one of the strings is empty and the other it is not, we match it to a gaps. Looking at the prefixes of both strings Three possible decisions: Both character prefix are not gaps and add penalization if they are different, there is a gap in one or in the other, adding the proper penalization.

#### Big O efficiency

O(n)

### 13. Bellman-Ford's algorithm. Shortest Path

#### Definition

It a dynamic programming algorithm that computes the shortest from an initial vertex to all the other vertices in a graph. 

It is based in the following recurrence:

Base case
A[0][v] = +infinite
A[0][initial_node] = 0

General case:
i in [1,n-1]
v in [1,n]
A[i][v] = Min |   A[i-1][v]
              |   Min (w,v) in E such as A[i-1][w] + c[w][v]

It is the origin of the modern network routing algorithm like as rip and rip2.

#### What you need to know

* Weights of the graph can be negative as oppose to Dijkstra's algorithm.
* If the graph has negative cycles there is no solution to the problem. Negative cycles can be detected by performing an extra n iteration and verifying that there is an improvement in some of the results.
* Space can be optimized storing just the values from the previous iteration necessary to compute the next one. To reconstructe the shortest path we can run the algorithm on backwards.

#### Big O efficiency

O(m*n) m=n of edges n= n of vertices

It could be O(n^2) in sparse, graphs O(n^3) in dense graphs

### 14. Floyd-Marshall's algorithm. All pairs shortest path

#### Definition

It a dynamic programming algorithm that computes the shortest between from all the vertices to all the other vertices in a graph. 

It is based in the following recurrence:

Base case:
A[i][j][0] = if (i == j ) 0
             if (i != j) (i,j) in E exists -> Cost of (i,j)
             if (i != j) (i,j) in E does not exist -> infinitve

General case:
k in [1,n]
i in [1,n]
j in [1,n]
A[i][j][k] = Min | A[i][j][k-1]
                 | A[i][k][k-1] + A[k][j][k-1]

#### What you need to know

* Weights of the graph can be negative as oppose to Dijkstra's algorithm.
* If the graph has negative cycles there is no solution to the problem.  Negative cycles can be detected by performing by iterating on the diagonal (i==j) of the results when k = n. At least there will be one vertex i whose entry will be negative.

#### Big O efficiency

O(n^3)

### Note on All pairs shortest path asymptotic cost

N times Dijkstra's     O(m log(n) => O(n^2 log(n)) Sparse graph
                                     O(n^3 log(n)) Dense graph
N times Bellman-Ford's O(m n) => O(n^3) Sparse graph
                                 O(n^4) Dense graph

### 15. Johnson's algorithm. All pairs shortest path

#### Definition

 It solves the problem of shortest paths in a graph with negative weights in its edges by adding some weights to each edge so that the graph does no have negatives anymore.

1 - Create a fake node that is connected to all the other nodes with edges whose weight is zero.
2 - Compute the weights necessary to remove all negative edges. This is done by applying Bellman-Ford's algorithm from this fake node.
3 - Apply to each edge: C' = C + Pu - Pv for every edge (u,v) in E.
4 - Apply Optimized Dijstra's algorithm one time per vertex to compute all pairs shortest path.
5 - Apply the formula in 4 on backwards to obtain the actual paths for the original graph.  C = C' - Pu + Pv

#### What you need to know

* Much better than Floyd-Marshall's algorithm for sparse graph or Bellman-Ford's algorithm.

#### Big O efficiency

O(n) + O(n*m) + O(m) + O(n*m*log(n)) + O(n^2) = O(n*m*log(n)) => O(n^2 * log(n)) Sparse graph (Btter than Floyd-Marshall's algorithm)
                                                                 O(n^3 * log(n)) Dense graph

### 16. Travelling salesman problem

#### Definition

Given a complete undirected graph with non negative edges, the goal is to obtain the minimum cost tour, i.e. a permutation of the vertices, that visits each vertex in the graph just once.

A dynamic programming solution would follow the next recurrence:

Subproblems: for every destination j in 1..n  and every subset S of 1..n that contains j and 1 L(S,j) is defined as the length of the path from 1 to j that visits exactly once each vertex in S.

Let A be a 2-D array indexed by subsets S that contain 1 and j in 1...n

Base case:

A[S,1] = 0 if S == [1]
         +infinite if S != [1]  

for m in 2..n
for each subset s with cardinality m that contains 1
for each j in 1..n j!=1
     A[S,j] =  min k in S, k != j A[S/j][k] + Ckj

To obtain the final solution an extra computation from the final solution in A.

for j in 2..n
 [A[1...n][j]].min

#### What you need to know

* No polynominal time solution. Uses DP to solve the problem in a similar fashion to Bellman-Ford
  
#### Big O efficiency

DP: O(n^2*2^n) Brute force: O(n!)

## NP-Complete Problem. NonDeterministic polynomial time

### Definition

A problem is in NP if:

* Solutions always have length polynomial in the input size.
* Solution correctness can be verified in polynomial time.

### What you need to know

Strategies to prove that a problem T is NP-complete:

1. Find a known NP-problem T'
2. Prove that T reduces to T'. This implies that T at least as hard as  T' and hence T is NP-complete too.

Strategies to solve np complete problems:

1. Use domain expertise. Is there any special structure within the data in your domain that can be exploited. For example, Knacksack solution with a capacity of O(n), makes the solution O(n^2) or 2-SAT problem. A constraint satifaction problem. A bunch of clauses that restrict which values are valid in a set of variables.
2. Use Heuristics i.e. fast algorithms that are not guaranteed to be correct.
3. Solve in exponential time but faster than brute force search.

* Every np problem can be solved by brute force search in exponential time.
* Just one polynomial time algorithm that solves an np problem would solve every
  np problem efficiently by reduction i.e. it would prove NP = P.
* Examples: Knapsack, tsp.

### Knapsack problem. How to Approach to NP problem

1. Identify computationally tractable special cases. Example: knapsack instances with small capacity.
2. Heuristics: Greedy heuristic and DP heuristic.
3. Exponential time solution better than brute force. Example: O(n*W) DP solution vs O(2^n).

#### Greedy heuristic

1. Sort and reindex using a ratio vi/wi
2. Pack items in this order until one does not fit.
3. Return either the value from 2 or the maximum value item that fits the capacity.

Step 3 makes the algorithm to guarantee that the result obtained will be at least 50% of the optimal solution

#### Dynamic programming heuristic

Making assumptions about the input there are at least two approaches:

* Assumption in first dp solution to the knapsack problem ----> weights and knapsack capacity are integral -> the solution in algorithm number 10 applies O(n*W)

* Assuming the values of the knapsack are small and integral.
    1. Round each vi down to the nearest multiple of m. vi'=[vi/m].  m depends on an epsilon given by the client.
    2. Use DP to solve the knapsack instance with values v1',v2'...vn' capacities w1,w2,w3
    O(n^2 *  max vi')

Recurrence:
    i=0...n
    x=0...n*vmax
    S[i][x] minimum total size needed to achieve value >= x while using only the first i items or +infinite if not possible.

    S[i][x]= min{   S[i-1][x]
                {   W[i] + S[i-1][x-v[i]]  if v[i] = 0 if x < v[i]

## P Problem

### Definition

A problem that has solution in polynomial time

## NP vs P problems

### What you need to know

* Conjeture P != NP has not been proved yet.
* One of the most important open questions in mathematics and computer sciences.
* Reasons to believe the conjeture:
1. Psychological. If P = NP somebody would have prove by now.
2. Philosophical. If P = NP then finding a solutions would be as easy as verify one.
3. Mathematical. ??

## Local Search

### Definition

Let X= set of candidate solutions to a problem e.g. cuts of a graph, TSP tours... and a neighborhood such as for each x in X specify which y in X are its neighbours e.g. in the max cut problem x,y are neighbours cuts <=> differ by moving one vertex. in tsp x,y tours are neighbours <=> if differ by 2 edges

1. Let x be some initial solution
2. while the current solution x has a superior neighboring solution y set x := y
3. return the final locally optimal solution

### What you need to know

* Initial solution could be:
  * Random solution => run many independent trials of local search and return the best locally optimal solution found.
  * Best heuristic if available => Use local search to improve the already good solution as post processing step.
* How to select next neighbour:
  * Choose one at random
  * Choose the best one. The one that provides the biggest improvement.
* How to define a neighborhood? A compromise between solution quality and efficient searchability has to be made. With bigger neighborhoods implies slower to verify local optimality but there are fewer local optimum.

* Local search is not guarantee to converge in polynomial time.
* Local search converge if every local step improves some objective function
* In general local optimal solutions are not good aproximations to globally optimal ones.

## 2-SAT problem. Papadimitriou's algorithm

### Definition

Problem: Given n boolean variables x1,x2...xn and m clauses, we have to evaluate if for some combination of the values of those variables the n clauses hold.

Solution:
Repeat log2(n) times

* Choose a random initial assignment
* repeat 2*n^2 times:
* if current assignment satisfies all the clauses, halt and report this
* else pick arbitrary unsatisfied clause and flip the value of one of its variables [ choose between the two uniformly random]

If not found solution report "Unsatisfiable"

### What you need to know

* Runs in polynomial time
* Always correct on unsatisfiable instances.
* It can be reduced to compute strongly connected component.