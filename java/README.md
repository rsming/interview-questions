[Back](../README.md)

# Java questions

## Collections package


### How HashMap works

 - ``hashCode()`` / ``equals()`` contract
 - backet per ``hashCode``, backet stored in ``LinkedList<Map.Entry>``
 - bakets organised as an array of backets, and retrieved by index = ``hashCode()`` % initial map size

```HashMap``` is not thread safe. Use ``Collections.synchronizedMap()`` or ``java.util.concurrent.ConcurrentHashMap``

## Java Memory Model

http://tutorials.jenkov.com/java-concurrency/java-memory-model.html

The Java memory model used internally in the JVM divides memory between thread stacks and the heap.
Each thread running in the Java virtual machine has its own thread stack.

The thread stack also contains all local variables for each method being executed (all methods on the call stack). A thread can only access it's own thread stack. Local variables created by a thread are invisible to all other threads than the thread who created it. Even if two threads are executing the exact same code, the two threads will still create the local variables of that code in each their own thread stack. Thus, each thread has its own version of each local variable.

## Functional Programming


## Inheritance / Incapsulation / Polymorphism


## Overloading / Overwriting


## Garbage Collector

 - Serial Garbage Collector
 
 This is the simplest GC implementation, as it basically works with a single thread. As a result, this GC implementation freezes all application threads when it runs. 
 
 - Parallel Garbage Collector
 
 Uses multiple threads for managing heap space. But it also freezes other application threads while performing GC.
 
 - CMS Garbage Collector
 
 The Concurrent Mark Sweep (CMS) implementation uses multiple garbage collector threads.
 
 - G1 Garbage Collector
 
 G1 (Garbage First) Garbage Collector is designed for applications running on multi-processor machines with large memory space. It’s available since JDK7 Update 4 and in later releases.
 
G1 collector will replace the CMS collector since it’s more performance efficient.

 1. unreferenced objects are identified and marked as ready for GC
 2. GCs implement a generational garbage collection strategy that categorizes objects by age.
 
  - Young Generation: Newly created objects start in the Young Generation
  - Old Generation: Objects that are long-lived are eventually moved from the Young Generation to the Old Generation
  - Permanent Generation: Metadata such as classes and methods are stored in the Permanent Generation.
 
Unreferenced objects:

 - By nulling a reference
 - By assigning a reference to another
 - By anonymous object
 
## What is new in Java 11
