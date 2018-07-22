# Parallel Programming

## Parallel Programming vs concurrent programming

Parallel program - uses parallel hardware to execute computation more quickly. Efficiency is its main concern.

Concurrent Program - may o may not execute multiple executions at the same time. Improves modularity, responsiveness or maintainability.

Parallel (Speed up)
- Division into subproblems.
- Optimal use of parallel hardware.
- Examples: Matrix multiplication, big data

Concurrent (Convenience)
- when can an execution start
- how can information exchange occur
- how to manage access to shared resources
- Examples: web servers, UI, Databases

##OS definition
## Definition	
Software that manages hardware and software resources, and schedules program execution.

## Process
### Definition	

An instance of a program that is executing in the OS.

The same program can be started as a process more than once, or even simultaneously in the same OS. The OS multiplexes many different processes and a limited number of CPUs, so that they get time slices of executions. This mecanishm is called multitasking.

Two different processes can not access earch other's memory directly - they are isolated.

Parallel programming vs Concurrent programming

## Thread
### Definition	

Each process can contain multiple independent concurrecy units called threads.

Threads can be started from within the same space program, and they share the same memory address space.

Each thread has a program counter and a program stack.

Each JVM process starts with a main thread. 


## Benchmarking parallel programs

### Definition
Computes perfomance metrics for parts of a program	

### Need to know
Performance measure is subject to many factors:
* Processor speed
* Number of processors
* Memory access latency and throughtput
* Cache behaviour(Several L1 L2 caches before the main memory)
* Runtime behaviour. Unexpected tasks that affect our programs from the OS or JVM (e.g. garbage collection, JIT compilation, thread scheduling...)

Measuring performance is a random variable. There are several ways to mitigate this:
* multiple repetitions  
* statistical treatment - computing mean and variance
* eliminating outliers
* ensuring a steady state by warming up the program (program runs long enough).
* prevent anomalies such as GC by allocating enought memory beforehand, disable JIT compilation or disable agressive compilations




