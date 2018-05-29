# Data Structures

## Array

### Definition
* Collection of elements (values or variables) consecutevily allocated in memory, each identified by, most commonly 0 based, index. An array is stored so that the position of each element can be computed from its index tuple by a mathematical formula.
* Based on tuples from set theory.

		
### Need to know

* Optimal for indexing; bad at searching, inserting, and deleting (except at the end).
* **Static arrays** or one dimensional arrays, Are static in size, meaning that they are declared with a fixed size.
* **Dynamic arrays** are like one dimensional arrays, but have reserved space for additional elements. If a dynamic array is full, it copies it&rsquo;s contents to a larger array.
* **Two dimensional arrays** have x and y indices like a grid or nested arrays.

| Big O Cost       | Linear Array  | Dynamic Array  |
| -----------------|:-------------:| --------------:|
| Indexing         | O(1)          | O(1)           |
| Search           | O(n)          | O(n)           |
| Optimized Search | O(log n)      | O(log n)       |
| Insertion        | n/a           | O(n)           |

## Linked List

### Definition
* Node based collection of elements where every node stores data a reference to other nodes.
* Nodes, at its most basic it has one data and one reference (another node). These are called single linked list.

		
### Need to know

* Designed to optimize insertion and deletion, slow at indexing and searching.
* **Doubly linked list** has nodes that reference the previous node.
* **Circularly linked list** is simple linked list whose **tail**, the last node, references the **head**, the first node.</li>

### Time cost using Big O notation 

| Big O Cost           | Linked List   | 
| ---------------------|:-------------:| 
| Indexing             | O(n)          | 
| Search               | O(n)          | 
| Insert first or last | O(1)          |
| Delete first or last | O(1)          |
| Insertion            | O(n)          | 
| Delete               | O(n)          | 

## Stack

### Definition
* Commonly implemented with linked lists but can be made from arrays too.
* Stacks are **last in, first out** (LIFO) data structures.
* Made with a linked list by having the head be the only place for insertion and removal.
		
## Queue

### Definition
* It can be implemented with a linked list or an array.
* Queues are a **first in, first out** (FIFO) data structure
* Made with a doubly linked list that only removes from head and adds to tail.

## Binary Tree

### Definition
* It is a tree like data structure where every node has at most two children.
		
### Need to know

* Designed to optimize searching and sorting.
* A **degenerate tree** is an unbalanced tree, which if entirely one-sided is a essentially a linked list.
* Used to make **binary search trees**.
* A binary tree that uses comparable keys to assign which direction a child is.
* Left child has a key smaller than it&rsquo;s parent node.
* Right child has a key greater than it&rsquo;s parent node.
* There can be no duplicate node.
* Tree traversal can be done in preorder, inorder and postorder
* It is usually self-balanced. Automatically keeps its height (maximal number of levels below the root) small in the face of arbitrary item insertions and deletions.
* Because of the above it is more likely to be used as a data structure than a binary tree.

### Time cost using Big O notation 

| Big O Cost           | Average(No rebalance)   | Worse | 
| ---------------------|:-----------------------:|:------| 
| Indexing             | O(log n)                | O(n)  |
| Search               | O(log n)                | O(n)  |
| Insertion            | O(log n)                | O(n)  | 
| Delete               | O(log n)                | O(n)  |

## Heap

### Definition
*  Tree-based data structure that satisfies the heap property: if P is a parent node of C, then the key (the value) of P is either greater than or equal to (in a max heap) or less than or equal to (in a min heap) the key of C.
					
### Need to know
* The heap is one maximally efficient implementation of an abstract data type called a priority queue.
* There is no implied ordering between siblings or cousins and no implied sequence for an in-order traversal. (as there would be in, e.g., a binary search tree)
* Heaps where the parent key is greater than or equal to (≥) the child keys are called max-heaps; those where it is less than or equal to (≤) are called min-heaps.
* Binary heaps are also commonly employed in the heapsort sorting algorithm, which is an in-place algorithm owing to the fact that binary heaps can be implemented as an implicit data structure, storing keys in an array and using their relative positions within that array to represent child-parent relationships.
* Used to implement priority queues.

### Time cost using Big O notation 

| Big O Cost           | Average(No rebalance)   | Worse | 
| ---------------------|:-----------------------:|:------| 
| Indexing             | O(n)                    | O(n)  |
| Search               | O(n)                    | O(n)  |
| Search  Min          | O(1)                    | O(1)  |
| Insertion            | O(log n)                | O(n)  | 
| Delete               | O(log n)                | O(n)  |

## B-Tree

### Definition
* Generalization of binary tree. It is a tree like data structure where every node has at most B children.

## Hash Table

### Definition
* Stores data with key value pairs.
* **Hash functions** accept a key and return an output unique only to that specific key.
* This is known as **hashing**, which is the concept that an input and an output have a one-to-one correspondence to map information.
* Hash functions return a unique address in memory for that data.
					
### Need to know
* Designed to optimize searching, insertion, and deletion.
* **Hash collisions** are when a hash function returns the same output for two distinct outputs. All hash functions have this problem. This is often accommodated for by having the hash tables be very large.
* Hashes are important for associative arrays and database indexing.

### Time cost using Big O notation 

| Big O Cost           | Average(No rebalance)   | Worse | 
| ---------------------|:-----------------------:|:------| 
| Indexing             | O(1)                    | O(n)  |
| Search               | O(1)                    | O(n)  |
| Insertion            | O(1)                    | O(n)  | 
| Delete               | O(1)                    | O(n)  |

## Graph

### Definition
A graph data structure consists of a finite set of nodes, together with a set of unordered pairs of these nodes for an undirected graph or a set of ordered pairs for a directed graph. These pairs are known as edges for an undirected graph and as directed edges for a directed graph.
					
### Need to know
* It can be implemented using an adjacency list or a matrix.

### Time cost using Big O notation 

| Big O Cost           | Adjacency list   | Adjacency  matrix | 
| ---------------------|:----------------:|:------------------| 
| Store graph          | O(|V|+|E|)       | O(|V|^{2})        |
| Add vertex           | O(1)             | O(|V|^{2})        |
| Add edge             | O(1)             | O(1)              | 
| Remove vertex        | O(|E|)           | O(|V|^{2})        |
| Remove edge          | O(|V|)           | O(1)              |
