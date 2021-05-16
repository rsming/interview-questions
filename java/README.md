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
https://www.baeldung.com/java-stack-heap

The Java memory model used internally in the JVM divides memory between thread stacks and the heap.
Each thread running in the Java virtual machine has its own thread stack.

The thread stack also contains all local variables for each method being executed (all methods on the call stack). A thread can only access it's own thread stack. Local variables created by a thread are invisible to all other threads than the thread who created it. Even if two threads are executing the exact same code, the two threads will still create the local variables of that code in each their own thread stack. Thus, each thread has its own version of each local variable.

### Stack Memory

 * It grows and shrinks as new methods are called and returned respectively
 * Variables inside stack exist only as long as the method that created them is running
 * It's automatically allocated and deallocated when method finishes execution
 * If this memory is full, Java throws `java.lang.StackOverFlowError`
 * Access to this memory is fast when compared to heap memory
 * This memory is threadsafe as each thread operates in its own stack

### Heap Space

Heap space in Java is used for dynamic memory allocation for Java objects and JRE classes at the runtime. New objects are always created in heap space and the references to this objects are stored in stack memory.

 * It's accessed via complex memory management techniques that include Young Generation, Old or Tenured Generation, and Permanent Generation
 * If heap space is full, Java throws java.lang.OutOfMemoryError
 * Access to this memory is relatively slower than stack memory
 * This memory, in contrast to stack, isn't automatically deallocated. It needs Garbage Collector to free up unused objects so as to keep the efficiency of the memory usage
 * Unlike stack, a heap isn't threadsafe and needs to be guarded by properly synchronizing the code

Memory model is further broken into smaller parts called generations:

 * `Young Generation` – this is where all new objects are allocated and aged. A minor Garbage collection occurs when this fills up
 * `Old or Tenured Generation` – this is where long surviving objects are stored. When objects are stored in the Young Generation, a threshold for the object's age is set and when that threshold is reached, the object is moved to the old generation
 * `Permanent Generation` – this consists of JVM metadata for the runtime classes and application methods

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
