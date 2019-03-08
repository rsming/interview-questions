[Back](../README.md)

# Multithreading questions

## concurency package


## What is volatile


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
