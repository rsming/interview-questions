[Back](../README.md)

# Multithreading questions

## concurency package


## What is volatile

The Java `volatile` keyword is used to mark a Java variable as "being stored in main memory". More precisely that means, that every read of a volatile variable will be read from the computer's main memory, and not from the CPU cache, and that every write to a volatile variable will be written to main memory, and not just to the CPU cache.

`volatile` guarantees order of variables initialisation, which can be changed by optimiser.

## Starvation

Starvation describes a situation where a thread is unable to gain regular access to shared resources and is unable to make progress. This happens when shared resources are made unavailable for long periods by "greedy" threads. For example, suppose an object provides a synchronized method that often takes a long time to return. If one thread invokes this method frequently, other threads that also need frequent synchronized access to the same object will often be blocked.

## Livelock

A thread often acts in response to the action of another thread. If the other thread's action is also a response to the action of another thread, then `livelock` may result. As with deadlock, livelocked threads are unable to make further progress. However, the threads are not blocked — they are simply too busy responding to each other to resume work. This is comparable to two people attempting to pass each other in a corridor: Alphonse moves to his left to let Gaston pass, while Gaston moves to his right to let Alphonse pass. Seeing that they are still blocking each other, Alphone moves to his right, while Gaston moves to his left. They're still blocking each other, so...

## Deadlock

A `lock` occurs when multiple processes try to access the same resource at the same time.
One process loses out and must wait for the other to finish.
A `deadlock` occurs when the waiting process is still holding on to another resource that the first needs before it can finish.

## ThreadLocal

The `TheadLocal` construct allows us to store data that will be accessible only by a specific thread.

## What new in multithreading in Java 8


## Explain Executors

```java
@Override
public DataSnapshot getDataSnapshot() throws DataAccessTimeoutException {
	ExecutorService executor = Executors.newFixedThreadPool(4);
	Future<Page<DailyQuote>> firstTask = executor.submit(() -> this.repository.findAll());
	....
  	try {
		DataSnapshot snapshot = new DataSnapshot();
		snapshot.setFirstResult(firstTask.get(10, TimeUnit.SECONDS). ... .findFirst().orElseGet(null));
		...
		return snapshot;
	} catch (InterruptedException | ExecutionException | TimeoutException exc) {
		throw new DataAccessTimeoutException(exc);
	} finally {
		executor.shutdownNow();
	}
}
```
