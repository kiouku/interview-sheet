
# Asymptotic computational complexity

Asymptotic computational complexity is the usage of asymptotic analysis (is a method of describing limiting behavior) for the estimation of computational complexity of algorithms and computational problems, commonly associated with the usage of the big O notation.


# Algorithm implementations

## Recursive Algorithms

### Definition
An algorithm that calls itself in its definition.


* **Recursive case** a conditional statement that is used to trigger the recursion.
* **Base case** a conditional statement that is used to break the recursion.

### What you need to know

* **Stack level too deep** and **stack overflow**.
* It means that your base case was never triggered because it was faulty or the problem was so massive you ran out of RAM before reaching it.
* Knowing whether or not you will reach a base case is integral to correctly using recursion.
* Often used in Depth First Search
* **Tail recursion and tail call elimination**

## Iterative Algorithms

### Definition
An algorithm that is called repeatedly but for a finite number of times, each time being a single iteration. Often used to move incrementally through a data set.

### What you need to know
* Generally you will see iteration as loops, for, while, and until statements.
* Think of iteration as moving one at a time through a set.
* Often used to move through an array.

## Recursion vs Iteration
* The differences between recursion and iteration can be confusing to distinguish since both can be used to implement the other.
* Recursion is, usually, more expressive and easier to implement.
* Iteration uses less memory.

* **Functional languages** tend to use recursion. (i.e. Haskell)
* **Imperative languages** tend to use iteration. (i.e. Java)
* Tail recursion. Tail call elimination.Tail calls can be implemented without adding a new stack frame to the call stack. Most of the frame of the current procedure is no longer needed, and can be replaced by the frame of the tail call.
* Check out this <a href="http://stackoverflow.com/questions/19794739/what-is-the-difference-between-iteration-and-recursion">Stack Overflow post</a> for more info.


### Pseudo Code of Moving Through an Array (this is why iteration is used for this

~~~~
Recursion                         | Iteration
----------------------------------|----------------------------------
recursive method (array, n)       | iterative method (array)
  if array[n] is not nil          |   for n from 0 to size of array
    print array[n]                |     print(array[n])
    recursive method(array, n+1)  |
  else                            |
    exit loop                     |
~~~~

# Algorithm Design paradigms
High level problem-solving strategies that cut across multiple applications/ different domains.

- Divide and Conquer
- Randomized Algorithms
- Greedy Algorithms
- Dynamic Programming and Memoization

## Divide and Conquer

### Definition
It is based on the idea of dividing a problem into smaller subproblems and then apply the same strategy to these subproblems until the subproblems are small enough that the resolution of the problem is trivial. Afterwards the results of the subproblems are combined to generate the solution to the original problem.

### What you need to know
- Example: Quicksort, Mergesort

## Randomized Algorithm

### Definition
The idea of making random choices within an algorithm that leads to a more practical and efficient solution.

### What you need to know
* Example: Randomized quicksort with a random pivot element.

## Greedy Algorithm

### Definition
Makes a sequence of myopic decisions, meaning in the short term these decisions provide the best result at the moment and then expect this to generate the best result to the problem.

### What you need to know
* Most of them are not correct. Correctness difficult to prove.
* Used to find the optimal solution for a given problem.
* Generally used on sets of data where only a small proportion of the information evaluated meets the desired result.
* Often a greedy algorithm can help to reduce the Big O of an algorithm.
* Examples: Dijkstra's shortest path algorithm, Prim's algorithm, job scheduler problem, coin change problem, optimal caching.

## Dynamic Programming and Memoization

### Definition
It is a method for solving a complex problem by breaking it down into a collection of simpler subproblems, solving each of those subproblems just once, and storing their solutions. 
The next time the same subproblem occurs, instead of recomputing its solution, one simply looks up the previously computed solution, thereby saving computation time at the expense of a (hopefully) modest expenditure in storage space.

* Find the recursion in the problem.
* Top-down: store the answer for each subproblem in a table to avoid having to recompute them.
* Bottom-up: Find the right order to evaluate the results so that partial results are available when needed.


### What you need to know:</h4>

* Memoization is a term describing an optimization technique where you cache previously computed results, and return the cached result when the same computation is needed again. 
* Dynamic programming is typically implemented using tabulation, but can also be implemented using memoization.
* When using tabulation you solve the problem "bottom up", i.e., by solving all related sub-problems first, typically by filling up an n-dimensional table. Based on the results in the table, the solution to the "top" / original problemis then computed.
* When using memoization, a map of already solved sub problems is maintained. You do it "top down" in the sense that yousolve the "top" problem first (which typically recurses down to solve the sub-problems).

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
Average Case Sort: O(n<sup>2</sup>)
Worst Case Sort: O(n<sup>2</sup>)
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

Best Case Sort: O(n<sup>2</sup>)
Average Case Sort: O(n<sup>2</sup>)
Worst Case Sort: O(n<sup>2</sup>)
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
Best Case Sort: O(n<sup>2</sup>)
Average Case Sort: O(n<sup>2</sup>)
Worst Case Sort: O(n<sup>2</sup>)
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
Worst Case Sort: O(n<sup>2</sup>)

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

## Graph related algorithms

### 1. Breadth First Search

#### Definition

An algorithm that searches a tree (or graph) by searching levels of the tree first, starting at the root.

* It finds every node on the same level, most often moving left to right.
* While doing this it tracks the children nodes of the nodes on the current level.

#### What you need to know
* It can be used to computed shortest path to every node in graph with edges of weight 1.
* Optimal for searching a tree that is wider than it is deep.
* Uses a queue to store information about the tree while it traverses a tree.
* Because it uses a queue it is more memory intensive than **depth first search**.
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
* Once it cannot go further left it begins evaluating the stack.

#### Big O efficiency
O(|E| + |V|)


## Breadth First Search Vs. Depth First Search

* The simple answer to this question is that it depends on the size and shape of the tree.
* For wide, shallow trees use Breadth First Search
* For deep, narrow trees use Depth First Search

#### Nuances

* Because BFS uses queues to store information about the nodes and its children, it could use more memory than is available on your computer. (But you probably won&rsquo;t have to worry about this.)
* If using a DFS on a tree that is very deep you might go unnecessarily deep in the search. See <a href="http://xkcd.com/761/">xkcd</a> for more information.
* Breadth First Search tends to be a looping algorithm.
* Depth First Search tends to be a recursive algorithm.

### 3. Dijkstra's algorithm. Computing the shortest path problem.

#### Definition

Traveses the graph as breadth search with the peculiarity of applying Dijstra greedy criteria to select the next node to be procesed. Dijkstra Greedy criterion is the sum of the shortest path until the previous node plus the weight of the edge that connects to the still unvisited node.

#### What you need to know:

* It works in any directed graph with non-negative edge lengths
* It computes the shortest paths from a source vertex to all other vertices.
* It can be optimized to linear time by using a heap where each vertex not visited connected to a vertex already visited is stored using as key the Dijkstra greedy criteria for that node.

#### Big O efficiency
* Naive implementation O(|E| + |V|)
* With heap O(|E| * log|V|)

### 3. Prim's algorithm. Computing the Minimum Spanning Tree problem.

#### Definition

#### What you need to know:

* It works only with undirected graphs.

#### Big O efficiency
* Naive implementation O(|E| + |V|)
* With heap O(|E| * log|V|)

## Montecarlo estimation

#### Definition
Monte Carlo methods are a broad class of computational algorithms that rely on repeated random sampling to obtain numerical results.

#### What you need to know
* Example: the estimation of Pi.

~~~~
The area of the square is 1 unit sq while that of circle is pi * (1/2)^2 = pi/4

For a very large number of generated points:

pi = 4 * num/num of point generated

By Pythagorean Theorem we can compute the distance from the center of a circle to any point:

d = sqrt((x1 - x2)^2 + (y1 - y2)^2)

when radio is r = 1 and x2,y2 is the origin

x1^2 + y1^2 < 1
~~~~
