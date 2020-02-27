# Parallel Programming

## Parallel Programming vs concurrent programming

Parallel program - uses parallel hardware to execute computation more quickly. Efficiency is its main concern.

Concurrent Program - may o may not execute multiple executions at the same time. Improves modularity, responsiveness or maintainability.

Parallel (Speed up)

- Division into subproblems.
- Optimal use of parallel hardware.
- Examples: Matrix multiplication, big data

Concurrent (Convenience)

- when an execution can start
- how information exchange can occur
- how to manage access to shared resources
- Examples: web servers, UI, Databases

## Benchmarking parallel programs

### Definition

Computes perfomance metrics for parts of a program

### Need to know

Performance measure is subject to many factors:

- Processor speed
- Number of processors
- Memory access latency and throughtput
- Cache behaviour(Several L1 L2 caches before the main memory)
- Runtime behaviour. Unexpected tasks that affect our programs from the OS or JVM (e.g. garbage collection, JIT compilation, thread scheduling...)

Measuring performance is a random variable. There are several ways to mitigate this:

- multiple repetitions
- statistical treatment - computing mean and variance
- eliminating outliers
- ensuring a steady state by warming up the program (program runs long enough).
- prevent anomalies such as GC by allocating enought memory beforehand, disable JIT compilation or disable agressive compilations

## OS definition

### Definition

Software that manages hardware and software resources, and schedules program execution.

## Process

### Definition

An instance of a program that is executing in the OS.

The same program can be started as a process more than once, or even simultaneously in the same OS. The OS multiplexes many different processes and a limited number of CPUs, so that they get time slices of executions. This mecanishm is called multitasking.

Two different processes can not access earch other's memory directly - they are isolated.

## Thread

### Definition

Each process can contain multiple independent concurrecy units called threads.

Threads can be started from within the same program space, and they share the same memory address space.

Each thread has a program counter and a program stack.

Each JVM process starts with a main thread.

# Memory segments
The Von Neumann architecture is defined by the fact that both the machine instructions and data are stored in the same memory space. This fact necessitates dividing memory into text and data segments.

In modern operating systems, there are more than just these two segments. Most systems use a single text segment, but actually use up to three data segments, depending on the storage class of the data being stored there. The four segments can be described as follows:

- The code segment, also known as text segment contains the machine instructions of the program. The code can be thought of like the text of a novel: It tells the story of what the program does.
- The data segment contains the static data of the program, i.e. the variables that exist throughout program execution. Global variables in a C or C++ program are static, as are variables declared as static in C, C++, or Java.
- The stack segment contains the system stack, which is used as temporary storage. The stack is a simple data structure with a LIFO (last-in first-out) access policy. Items are only added to or removed from the "top" of the stack. Implementing a stack requires only a block of memory (e.g. an array in a HLL) and a stack pointer which tells us where the top of the stack is. In the MIPS architecture, the $sp register is designated as the stack pointer. Adding an element to the top of the stack is known as a push, and retrieving an item from the top is known as a pop. If we were to push the values 1, 2, 3, 4, and 5, and then do a single pop, the stack would appear as follows:
	    +---+
	    | 5 |
	    | 4 | <- sp
	    | 3 |
	    | 2 |
	    | 1 |
	    +---+
	    
- The heap segment is a pool of memory used for dynamically allocated memory, such as with malloc() in C or new in C++ and Java.
