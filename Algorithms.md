	
				<h2>Search Basics</h2>

				<h3>
					<strong>Breadth First Search</strong>
				</h3>

				<h4>Definition:</h4>

				<ul>
					<li>An algorithm that searches a tree (or graph) by searching levels of the tree first, starting at the root.

						<ul>
							<li>It finds every node on the same level, most often moving left to right.</li>
							<li>While doing this it tracks the children nodes of the nodes on the current level.</li>
							<li>When finished examining a level it moves to the left most node on the next level.</li>
							<li>The bottom-right most node is evaluated last (the node that is deepest and is farthest right of it&rsquo;s level).</li>
						</ul>
					</li>
				</ul>


				<h4>What you need to know:</h4>

				<ul>
					<li>Optimal for searching a tree that is wider than it is deep.</li>
					<li>Uses a queue to store information about the tree while it traverses a tree.
						<ul>
							<li>Because it uses a queue it is more memory intensive than
								<strong>depth first search</strong>.</li>
							<li>The queue uses more memory because it needs to stores pointers</li>
						</ul>
					</li>
				</ul>


				<h4>Big O efficiency:</h4>

				<ul>
					<li>Search: Breadth First Search: O(|E| + |V|)</li>
					<li>E is number of edges</li>
					<li>V is number of vertices</li>
				</ul>

				<h3>
					<strong>Depth First Search</strong>
				</h3>

				<h4>Definition:</h4>

				<ul>
					<li>An algorithm that searches a tree (or graph) by searching depth of the tree first, starting at the root.

						<ul>
							<li>It traverses left down a tree until it cannot go further.</li>
							<li>Once it reaches the end of a branch it traverses back up trying the right child of nodes on that branch, and if possible
								left from the right children.</li>
							<li>When finished examining a branch it moves to the node right of the root then tries to go left on all it&rsquo;s children
								until it reaches the bottom.</li>
							<li>The right most node is evaluated last (the node that is right of all it&rsquo;s ancestors).</li>
						</ul>
					</li>
				</ul>


				<h4>What you need to know:</h4>

				<ul>
					<li>Optimal for searching a tree that is deeper than it is wide.</li>
					<li>Uses a stack to push nodes onto.

						<ul>
							<li>Because a stack is LIFO it does not need to keep track of the nodes pointers and is therefore less memory intensive
								than breadth first search.</li>
							<li>Once it cannot go further left it begins evaluating the stack.</li>
						</ul>
					</li>
				</ul>


				<h4>Big O efficiency:</h4>

				<ul>
					<li>Search: Depth First Search: O(|E| + |V|)</li>
					<li>E is number of edges</li>
					<li>V is number of vertices</li>
				</ul>


				<h4>Breadth First Search Vs. Depth First Search</h4>

				<ul>
					<li>The simple answer to this question is that it depends on the size and shape of the tree.

						<ul>
							<li>For wide, shallow trees use Breadth First Search</li>
							<li>For deep, narrow trees use Depth First Search</li>
						</ul>
					</li>
				</ul>

				<h4>Nuances:</h4>

				<ul>
					<li>Because BFS uses queues to store information about the nodes and its children, it could use more memory than is available
						on your computer. (But you probably won&rsquo;t have to worry about this.)</li>
					<li>If using a DFS on a tree that is very deep you might go unnecessarily deep in the search. See
						<a href="http://xkcd.com/761/">xkcd</a> for more information.</li>
					<li>Breadth First Search tends to be a looping algorithm.</li>
					<li>Depth First Search tends to be a recursive algorithm.</li>
				</ul>

				<h2>Comparison sort algorithms</h2>

				<h3>
					<strong>Bubble Sort</strong>
				</h3>

				<h4>Definition:</h4>

				<ul>
					<li>It iterates left to right comparing every couple, moving the smaller element to the left.</li>
					<li>It repeats this process until it no longer moves and element to the left.</li>
				</ul>


				<h4>What you need to know:</h4>

				<ul>
					<li>While it is very simple to implement, it is the least efficient of the sorting methods.</li>
					<li>Know that it moves one space to the right comparing two elements at a time and moving the smaller on to left.</li>
					<li>Can be optimized to avoid up to 50% of the comparisons by starting from the last swap in the previous iteration</li>
					<li>Stable</li>
				</ul>

				<h4>Big O efficiency:</h4>

				<ul>
					<li>Best Case Sort: O(n)</li>
					<li>Average Case Sort: O(n
						<sup>2</sup>)</li>
					<li>Worst Case Sort: O(n
						<sup>2</sup>)</li>
					<li>Space: O(1)</li>
				</ul>

				<h3>
					<strong>Insertion Sort</strong>
				</h3>

				<h4>Definition:</h4>


				<ul>
					<li>Builds the final sorted array (or list) one item at a time.</li>
					<li>At each iteration, insertion sort removes one element from the input data, finds the location it belongs within the
						sorted list, and inserts it there. It repeats until no input elements remain.</li>
				</ul>

				<h4>What you need to know:</h4>

				<ul>
					<li>Efficient for (quite) small data sets, much like other quadratic sorting algorithms such as selection sort or bubble
						sort
					</li>
					<li>More efficient in practice than most other simple quadratic algorithms.</li>
					<li>Stable</li>
				</ul>

				<h4>Big O efficiency:</h4>

				<ul>
					<li>Best Case Sort: O(n
						<sup>2</sup>)</li>
					<li>Average Case Sort: O(n
						<sup>2</sup>)</li>
					<li>Worst Case Sort: O(n
						<sup>2</sup>)</li>
					<li>Space: O(1)</li>
				</ul>
				<h3>
					<strong>Selection Sort</strong>
				</h3>

				<h4>Definition:</h4>

				<ul>
					<li>The algorithm divides the input list into two parts: the sublist of items already sorted, which is built up from left
						to right at the front (left) of the list, and the sublist of items remaining to be sorted that occupy the rest of the
						list.
					</li>
					<li>Initially, the sorted sublist is empty and the unsorted sublist is the entire input list.</li>
					<li>The algorithm proceeds by finding the smallest (or largest, depending on sorting order) element in the unsorted sublist,
						exchanging (swapping) it with the leftmost unsorted element (putting it in sorted order), and moving the sublist boundaries
						one element to the right </li>
				</ul>

				<h4>What you need to know:</h4>

				<ul>
					<li>Generally performs worse than the similar insertion sort.</li>
					<li>Selection sort is noted for its simplicity, and it has performance advantages over more complicated algorithms in certain
						situations, particularly where auxiliary memory is limited.</li>
					<li>Unstable. Stable implementation can be done with additional data structure.</li>
				</ul>


				<h4>Big O efficiency:</h4>

				<ul>
					<li>Best Case Sort: O(n
						<sup>2</sup>)</li>
					<li>Average Case Sort: O(n
						<sup>2</sup>)</li>
					<li>Worst Case Sort: O(n
						<sup>2</sup>)</li>
					<li>Space: O(1)</li>
				</ul>

				<h3>
					<strong>Merge Sort</strong>
				</h3>

				<h4>Definition:</h4>

				<ul>
					<li>Divide the unsorted list into n sublists, each containing 1 element (a list of 1 element is considered sorted).</li>
					<li>Repeatedly merge sublists to produce new sorted sublists until there is only 1 sublist remaining. This will be the sorted
						list.
					</li>
				</ul>

				<h4>What you need to know:</h4>

				<ul>
					<li>Implementation of the divide and conquer algorithm stategy.</li>
					<li>Know that it divides all the data into as small possible sets then compares them.</li>
					<li>Most of the implementations stable sort</li>
				</ul>

				<h4>Big O efficiency:</h4>

				<ul>
					<li>Best Case Sort: O(n)</li>
					<li>Average Case Sort: O(n log n)</li>
					<li>Worst Case Sort: O(n log n)</li>
				</ul>

				<h3>
					<strong>Quicksort</strong>
				</h3>

				<h4>Definition:</h4>

				<ul>
					<li>Pick an element, called a pivot, from the array.</li>
					<li>Partitioning: reorder the array so that all elements with values less than the pivot come before the pivot, while all
						elements with values greater than the pivot come after it (equal values can go either way). After this partitioning,
						the pivot is in its final position. This is called the partition operation.</li>
					<li>Recursively apply the above steps to the sub-array of elements with smaller values and separately to the sub-array of
						elements with greater values.</li>
				</ul>

				<h4>What you need to know:</h4>

				<ul>
					<li>While it has the same Big O as (or worse in some cases) many other sorting algorithms it is often faster in practice
						than many other sorting algorithms, such as merge sort.</li>
					<li>Know that it halves the data set by the average continuously until all the information is sorted.</li>
					<li>Unstable</li>
				</ul>

				<h4>Big O efficiency:</h4>

				<ul>
					<li>Best Case Sort: O(n)</li>
					<li>Average Case Sort: O(n log n)</li>
					<li>Worst Case Sort: O(n
						<sup>2</sup>)</li>
				</ul>

				<h4>Merge Sort vs Quicksort</h4>
				<ul>
					<li>Quicksort is likely faster in practice.</li>
					<li>Merge Sort divides the set into the smallest possible groups immediately then reconstructs the incrementally as it sorts
						the groupings.</li>
					<li>Quicksort continually divides the set by the average, until the set is recursively sorted.</li>
				</ul>

				<h4>Merge Sort vs Heapsort</h4>
				<ul>

					<li> Merge sort requires O(n) auxiliary space, but heapsort requires only a constant amount. Heapsort typically runs faster
						in practice on machines with small or slow data caches, and does not require as much external memory.</li>
					<li>Merge sort on arrays has considerably better data cache performance, often outperforming heapsort on modern desktop
						computers because merge sort frequently accesses contiguous memory locations (good locality of reference); heapsort
						references are spread throughout the heap.</li>
					<li>Heapsort is not a stable sort; merge sort is stable.</li>
					<li>Merge sort parallelizes well and can achieve close to linear speedup with a trivial implementation; heapsort is not
						an obvious candidate for a parallel algorithm.</li>
					<li>Merge sort can be adapted to operate on singly linked lists with O(1) extra space. Heapsort can be adapted to operate
						on doubly linked lists with only O(1) extra space overhead.</li>
					<li>Merge sort is used in external sorting; heapsort is not. Locality of reference is the issue.</li>
				</ul>

				<h3>
					<strong>Heap Sort</strong>
				</h3>

				<h4>Definition:</h4>

				<ul>
					<li>A comparison based sorting algorithm

						<ul>
							<li>In the first step, a heap is built out of the data. The heap is often placed in an array with the layout of a complete
								binary tree. The complete binary tree maps the binary tree structure into the array indices; each array index represents
								a node; the index of the node's parent, left child branch, or right child branch are simple expressions. For a zero-based
								array, the root node is stored at index 0; if i is the index of the current node, then
							</li>
							<li> In the second step, a sorted array is created by repeatedly removing the largest element from the heap (the root of
								the heap), and inserting it into the array. The heap is updated after each removal to maintain the heap property.
								Once all objects have been removed from the heap, the result is a sorted array.
							</li>
							<li>Parent(i) = floor((i-1) / 2) where floor functions map a real number to the smallest leading integer. iLeftChild(i)
								= 2*i + 1 iRightChild(i) = 2*i + 2</li>
						</ul>
					</li>
				</ul>
				<h4>What you need to know:</h4>

				<ul>
					<li>Heapsort can be thought of as an improved selection sort.</li>
					<li>Although somewhat slower in practice on most machines than a well-implemented quicksort, it has the advantage of a more
						favorable worst-case O(n log n) runtime</li>
					<li>Not a stable sort</li>
				</ul>

				<h4>Big O efficiency:</h4>

				<ul>
					<li>Best Case Sort: O(n log n) O(n) if equal keys</li>
					<li>Average Case Sort: O(n log n),</li>
					<li>Worst Case Sort: O(n log n)</li>
					<li>Space: O(1)</li>
				</ul>

				<h2>Non comparison sort algorithms</h2>

				<h3>
					<strong>Pigeonhole Sort</strong>
				</h3>
				<h4>Definition:</h4>
				<ul>
					<li>Given an array of values to be sorted, set up an auxiliary array of initially empty "pigeonholes," one pigeonhole for
						each key through the range of the original array.</li>
					<li>Going over the original array, put each value into the pigeonhole corresponding to its key, such that each pigeonhole
						eventually contains a list of all values with that key.</li>
					<li>Iterate over the pigeonhole array in order, and put elements from non-empty pigeonholes back into the original array.</li>
				</ul>

				<h4>What you need to know:</h4>

				<ul>
					<li>Suitable for sorting lists of elements where the number of elements (n) and the length of the range of possible key
						values (N) are approximately the same.</li>
					<li>Stable</li>
				</ul>

				<h4>Big O efficiency:</h4>

				<ul>
					<li>Worst Case Sort: O(N+n) where N is the range of key values and n is the input size</li>
					<li>Space: O(N+n)</li>
				</ul>


				<h2>Basic Types of Algorithms</h2>

				<h3>
					Asymptotic computational
				</h3>
				<p>Asymptotic computational complexity is the usage of asymptotic analysis (is a method of describing limiting behavior)
					for the estimation of computational complexity of algorithms and computational problems, commonly associated with the
					usage of the big O notation.
				</p>

				<h3>
					<strong>Recursive Algorithms</strong>
				</h3>

				<h4>Definition:</h4>

				<ul>
					<li>An algorithm that calls itself in its definition.

						<ul>
							<li>
								<strong>Recursive case</strong> a conditional statement that is used to trigger the recursion.</li>
							<li>
								<strong>Base case</strong> a conditional statement that is used to break the recursion.</li>
						</ul>
					</li>
				</ul>

				<h4>What you need to know:</h4>

				<ul>
					<li>
						<strong>Stack level too deep</strong> and
						<strong>stack overflow</strong>.

						<ul>
							<li>It means that your base case was never triggered because it was faulty or the problem was so massive you ran out of
								RAM before reaching it.</li>
							<li>Knowing whether or not you will reach a base case is integral to correctly using recursion.</li>
							<li>Often used in Depth First Search</li>
						</ul>
					</li>
					<li>
						<strong>Tail recursion and tail call elimination</strong>
					</li>
				</ul>

				<h3>
					<strong>Iterative Algorithms</strong>
				</h3>

				<h4>Definition:</h4>

				<ul>
					<li>An algorithm that is called repeatedly but for a finite number of times, each time being a single iteration.</li>
					<li>Often used to move incrementally through a data set.</li>
				</ul>

				<h4>What you need to know:</h4>

				<ul>
					<li>Generally you will see iteration as loops, for, while, and until statements.</li>
					<li>Think of iteration as moving one at a time through a set.</li>
					<li>Often used to move through an array.</li>
				</ul>

				<h4>Recursion Vs. Iteration</h4>

				<ul>
					<li>The differences between recursion and iteration can be confusing to distinguish since both can be used to implement
						the other. But know that,

						<ul>
							<li>Recursion is, usually, more expressive and easier to implement.</li>
							<li>Iteration uses less memory.</li>
						</ul>
					</li>
					<li>
						<strong>Functional languages</strong> tend to use recursion. (i.e. Haskell)</li>
					<li>
						<strong>Imperative languages</strong> tend to use iteration. (i.e. Ruby)</li>
					<li>
						Tail recursion. Tail call elimination.Tail calls can be implemented without adding a new stack frame to the call stack. Most
						of the frame of the current procedure is no longer needed, and can be replaced by the frame of the tail cal </li>
					<li>Check out this
						<a href="http://stackoverflow.com/questions/19794739/what-is-the-difference-between-iteration-and-recursion">Stack Overflow post</a> for more info.</li>
				</ul>

				<h4>Pseudo Code of Moving Through an Array (this is why iteration is used for this)</h4>

				<figure class='code'>
					<div class="highlight">
						<table>
							<tr>
								<td class="gutter">
									<pre class="line-numbers"><span class='line-number'>1</span>
										<span class='line-number'>2</span>
										<span class='line-number'>3</span>
										<span class='line-number'>4</span>
										<meta name="description" content="Studying for a Tech Interview Sucks, so Here&rsquo;s a Cheat Sheet to Help This list is meant to be a both a quick guide and reference for further &hellip;">
									
										<span class='line-number'>5</span>
										<span class='line-number'>6</span>
										<span class='line-number'>7</span>
										<span class='line-number'>8</span>
										</pre>
								</td>
								<td class='code'>
									<pre><code class=''><span class='line'>Recursion                         | Iteration
															</span><span class='line'>----------------------------------|----------------------------------
															</span><span class='line'>recursive method (array, n)       | iterative method (array)
															</span><span class='line'>  if array[n] is not nil          |   for n from 0 to size of array
															</span><span class='line'>    print array[n]                |     print(array[n])
															</span><span class='line'>    recursive method(array, n+1)  |
															</span><span class='line'>  else                            |
															</span><span class='line'>    exit loop                     |</span></code></pre>
								</td>
							</tr>
						</table>
					</div>
				</figure>

				<h3>
					<strong>Greedy Algorithm</strong>
				</h3>

				<h4>Definition:</h4>

				<ul>
					<li>An algorithm that, while executing, selects only the information that meets a certain criteria.</li>
					<li>The general five components, taken from
						<a href="http://en.wikipedia.org/wiki/Greedy_algorithm#Specifics">Wikipedia</a>:

						<ul>
							<li>A candidate set, from which a solution is created.</li>
							<li>A selection function, which chooses the best candidate to be added to the solution.</li>
							<li>A feasibility function, that is used to determine if a candidate can be used to contribute to a solution.</li>
							<li>An objective function, which assigns a value to a solution, or a partial solution.</li>
							<li>A solution function, which will indicate when we have discovered a complete solution.</li>
						</ul>
					</li>
				</ul>

				<h4>What you need to know:</h4>

				<ul>
					<li>Used to find the optimal solution for a given problem.</li>
					<li>Generally used on sets of data where only a small proportion of the information evaluated meets the desired result.</li>
					<li>Often a greedy algorithm can help to reduce the Big O of an algorithm.</li>
				</ul>

				<h4>Pseudo Code of a Greedy Algorithm to Find Largest Difference of any Two Numbers in an Array.</h4>

				<figure class='code'>
					<div class="highlight">
						<table>
							<tr>
								<td class="gutter">
									<pre class="line-numbers">
										<span class='line-number'>1</span>
										<span class='line-number'>2</span>
										<span class='line-number'>3</span>
										<span class='line-number'>4</span>
										<span class='line-number'>5</span>
										<span class='line-number'>6</span>
									</pre>
								</td>
								<td class='code'>
									<code class=''>
										<span class='line'>greedy algorithm (array)</span>
										<span class='line'>  var largest difference = 0</span>
										<span class='line'>  var new difference = find next difference (array[n], array[n+1])</span>
										<span class='line'>  largest difference = new difference if new difference is &gt; largest difference</span>
										<span class='line'>  repeat above two steps until all differences have been found</span>
										<span class='line'>  return largest difference</span>
									</code>
								</td>
							</tr>
						</table>
					</div>
				</figure>

				<p>This algorithm never needed to compare all the differences to one another, saving it an entire iteration.</p>


				<h3>
					<strong>Dynamic Programming</strong>
				</h3>

				<h4>Definition:</h4>

				<ul>
					<li>It is a method for solving a complex problem by breaking it down into a collection of simpler subproblems, solving each
						of those subproblems just once, and storing their solutions. </li>

					<li> The next time the same subproblem occurs, instead of recomputing its solution, one simply looks up the previously computed
						solution, thereby saving computation time at the expense of a (hopefully) modest expenditure in storage space.</li>
					<ul>
						<li>Find the recursion in the problem.</li>
						<li>Top-down: store the answer for each subproblem in a table to avoid having to recompute them.</li>
						<li>Bottom-up: Find the right order to evaluate the results so that partial results are available when needed.</li>
					</ul>
				</ul>

				<h4>What you need to know:</h4>

				<ul>
					<li>Memoization is a term describing an optimization technique where you cache previously computed results, and return the
						cached result when the same computation is needed again. </li>
					<li>Dynamic programming is typically implemented using tabulation, but can also be implemented using memoization.</li>
					<li>When using tabulation you solve the problem "bottom up", i.e., by solving all related sub-problems first, typically
						by filling up an n-dimensional table. Based on the results in the table, the solution to the "top" / original problem
						is then computed.</li>
					<li> When using memoization, a map of already solved sub problems is maintained. You do it "top down" in the sense that you
						solve the "top" problem first (which typically recurses down to solve the sub-problems).</li>
				</ul>
