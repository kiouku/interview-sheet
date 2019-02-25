
# Asymptotic computational complexity

Asymptotic computational complexity is the usage of asymptotic analysis (is a method of describing limiting behavior) for the estimation of computational complexity of algorithms and computational problems, commonly associated with the usage of the big O notation.

## Recursive Algorithms Complexity. The master method

### Definition

Given that all subproblems x have equal size b.

Recurrence:

1. Base Case : T(n) <= a constant for all sufficiently small n
2. For all larger n :

        T(n) <= a * T(n/b) + O(n^d)
where
    a = number of recursive calls (>= 1)
    b = input size shrinkage factor ( > 1)
    d = exponent in running time of “combine step” (>=0) [a,b,d independent of n ]

        O(n^d * log(n)) if a = b^d
T(n) =  O(n^d)          if a < b^d
        O(n^logb(a))    if a > b^d

### Examples

~~~
int recursiveFun1(int n)
{
    if (n <= 0)
        return 1;
    else
        return 1 + recursiveFun1(n-1);
}
~~~~
This function is called recursively n times before reaching base case so its O(n), often called linear.
~~~~
int recursiveFun2(int n)
{
    if (n <= 0)
        return 1;
    else
        return 1 + recursiveFun2(n-5);
}
~~~~
This function is called n-5 for each time, so we deduct five from n before calling the function, but n-5 is also O(n). (Actually called order of n/5 times. And, O(n/5) = O(n) ).
~~~~
int recursiveFun3(int n)
{
    if (n <= 0)
        return 1;
    else
        return 1 + recursiveFun3(n/5);
}
~~~~
This function is log(n) base 5, for every time we divide by 5 before calling the function so its O(log(n))(base 5), often called logarithmic and most often Big O notation and complexity analysis uses base 2.

~~~~
void recursiveFun4(int n, int m, int o)
{
    if (n <= 0)
    {
        printf("%d, %d\n",m, o);
    }
    else
    {
        recursiveFun4(n-1, m+1, o);
        recursiveFun4(n-1, m, o+1);
    }
}
~~~~
This function is O(2^n), or exponential, since each function call calls itself twice unless it has been recursed n times.

~~~~
int recursiveFun5(int n)
{
    for (i = 0; i < n; i += 2) {
        // do something
    }

    if (n <= 0)
        return 1;
    else
        return 1 + recursiveFun5(n-5);
}
~~~~

 In this case, the for loop takes n/2 since we're increasing by 2, and the recursion take n-5 and since the for loop is called recursively therefore the time complexity is in (n-5) *(n/2) = (2n-10) * n = 2n^2- 10n, due to Asymptotic behavior and worst case scenario considerations or the upper bound that big O is striving for, we are only interested in the largest term so O(n^2).

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

* Divide and Conquer
* Randomized Algorithms
* Greedy Algorithms
* Dynamic Programming and Memoization

## Divide and Conquer

### Definition

It is based on the idea of dividing a problem into smaller subproblems and then apply the same strategy to these subproblems until the subproblems are small enough that the resolution of the problem is trivial. Afterwards the results of the subproblems are combined to generate the solution to the original problem.

### What you need to know

* Example: Quicksort, Mergesort

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
* Examples: Dijkstra's shortest path algorithm, Prim's algorithm,Kruskal's algorithm, job scheduler problem, coin change problem, huffman coding algorithm.

## Dynamic Programming and Memoization

### Definition

It is a method for solving a complex problem by breaking it down into a collection of simpler subproblems, solving each of those subproblems just once, and storing their solutions. 
The next time the same subproblem occurs usually via a recurrence, instead of recomputing its solution, one simply looks up the previously computed solution, thereby saving computation time at the expense of a (hopefully) modest expenditure in storage space.

* Find the recursion in the problem.
* Top-down: store the answer for each subproblem in a table to avoid having to recompute them.
* Bottom-up: Find the right order to evaluate the results so that partial results are available when needed.

### What you need to know:</h4>

* Memoization is a term describing an optimization technique where you cache previously computed results, and return the cached result when the same computation is needed again.
* Dynamic programming is typically implemented using tabulation, but can also be implemented using memoization.
* When using tabulation you solve the problem "bottom up", i.e., by solving all related sub-problems first, typically by filling up an n-dimensional table. Based on the results in the table, the solution to the "top" / original problemis then computed.
* When using memoization, a map of already solved sub problems is maintained. You do it "top down" in the sense that yousolve the "top" problem first (which typically recurses down to solve the sub-problems).

## Montecarlo estimation

### Definition

Monte Carlo methods are a class of algorithms that rely on repeated random sampling to obtain numerical results.

### What you need to know

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
