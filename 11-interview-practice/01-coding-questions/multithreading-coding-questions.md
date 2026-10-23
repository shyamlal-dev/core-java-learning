# Multithreading and Concurrency Coding Questions

These questions test thread safety, synchronization, coordination, visibility, atomicity, and modern concurrency utilities.

## 1. Build a Thread-Safe Counter

Implement a counter using:

- `synchronized`
- `ReentrantLock`
- `AtomicInteger`

### Requirements

- Run multiple incrementing threads.
- Verify the final counter value.
- Compare the three implementations.
- Avoid unnecessary synchronization.
- Explain which solution is suitable for a simple counter.

---

## 2. Print Odd and Even Numbers Using Two Threads

One thread must print odd numbers and another must print even numbers in sequence.

### Requirements

- Do not use busy waiting.
- Implement using `wait()` and `notifyAll()`.
- Implement another solution using `Lock` and `Condition`.
- Ensure correct termination.
- Handle spurious wakeups correctly.

---

## 3. Implement Producer-Consumer

Create producers and consumers sharing a bounded buffer.

### Requirements

- Block producers when the buffer is full.
- Block consumers when the buffer is empty.
- Avoid race conditions.
- Implement manually using `wait()` and `notifyAll()`.
- Implement another solution using `BlockingQueue`.

---

## 4. Create a Thread-Safe Bank Account

Multiple threads perform deposits and withdrawals on the same account.

### Requirements

- Prevent lost updates.
- Keep validation and modification atomic.
- Avoid locking unrelated operations.
- Prevent the balance from becoming invalid.
- Demonstrate why `volatile` alone is insufficient.

---

## 5. Demonstrate and Prevent Deadlock

Create a controlled deadlock using two shared resources.

Then prevent the deadlock using:

- Consistent lock ordering
- `tryLock()`
- Timeout-based failure handling

### Requirements

- Keep the demonstration predictable.
- Explain circular wait.
- Release acquired locks safely.
- Avoid swallowing interruption.

---

## 6. Execute Tasks Using a Thread Pool

Process independent tasks using `ExecutorService`.

### Requirements

- Use a fixed-size thread pool.
- Shut down the executor correctly.
- Handle failed tasks.
- Handle rejected tasks.
- Avoid creating one thread per task.
- Wait for termination safely.

---

## 7. Aggregate Results Using Callable and Future

Submit multiple calculations and combine their results.

### Requirements

- Use `Callable`.
- Handle task exceptions.
- Apply task timeouts.
- Cancel tasks that exceed the timeout.
- Shut down the executor safely.
- Preserve interruption status where required.

---

## 8. Build an Asynchronous Workflow

Using `CompletableFuture`:

1. Fetch employee details.
2. Fetch department details independently.
3. Combine both results.
4. Transform the final result.
5. Handle failures.
6. Apply a timeout.

### Requirements

- Avoid blocking intermediate operations.
- Avoid unnecessary calls to `get()` and `join()`.
- Use an appropriate executor.
- Handle partial failures clearly.

---

## 9. Implement a Read-Heavy Cache

Create a cache supporting concurrent reads and occasional writes.

### Requirements

- Implement one version using `ReadWriteLock`.
- Prevent partial updates.
- Define cache-miss behavior.
- Compare the design with `ConcurrentHashMap`.
- Avoid returning mutable cached values directly.

---

## 10. Build a Concurrent Task Tracker

Track tasks with the following statuses:

- Pending
- Running
- Completed
- Failed

### Requirements

- Multiple threads may update different tasks.
- Readers must see consistent task status.
- Avoid globally synchronizing the complete collection.
- Prevent invalid status transitions.
- Store failure information for failed tasks.

---

## 11. Demonstrate and Fix a Race Condition

Create a program that produces an incorrect result because of a race condition.

Then fix the issue and explain:

- Shared mutable state
- Atomicity
- Visibility
- Ordering
- Critical sections

### Requirements

- Demonstrate the incorrect result consistently where possible.
- Provide more than one valid solution.
- Compare the trade-offs of the solutions.

---

## 12. Implement Graceful Shutdown

Build a background worker that:

- Accepts tasks.
- Processes queued tasks.
- Stops accepting new tasks during shutdown.
- Completes or safely cancels pending work.
- Responds correctly to interruption.

### Requirements

- Do not silently ignore `InterruptedException`.
- Avoid leaving running threads after shutdown.
- Handle shutdown timeout.
- Make shutdown idempotent.

---

## 13. Create a Thread-Safe Singleton

Implement a lazily initialized singleton.

### Requirements

- Make initialization thread-safe.
- Implement using the initialization-on-demand holder pattern.
- Compare with double-checked locking.
- Explain the role of `volatile`.
- Prevent unnecessary synchronization after initialization.

---

## 14. Implement a Simple Rate Limiter

Create a thread-safe rate limiter.

### Requirements

- Limit operations within a configured time window.
- Support access from multiple threads.
- Avoid busy waiting.
- Keep time-dependent logic testable.
- Define behavior when the limit is exceeded.

---

## 15. Build a Parallel File Processor

Process multiple independent files concurrently.

### Requirements

- Limit concurrency using a thread pool.
- Capture success and failure for each file.
- Do not stop complete processing when one file fails.
- Support cancellation.
- Shut down resources gracefully.

---

## 16. Implement a Concurrent Inventory Reservation

Allow multiple threads to reserve and release product inventory.

### Requirements

- Inventory must never become negative.
- Check and update must be atomic.
- Avoid global locking across unrelated products.
- Record successful and failed reservations.
- Support safe concurrent reads.

---

## 17. Alternate Printing Using Three Threads

Use three threads to repeatedly print:

```text
ABCABCABC...
```

### Requirements

- Each thread must print only its assigned character.
- Output order must remain correct.
- Do not use busy waiting.
- Stop after a configured number of cycles.
- Handle interruption correctly.

---

## 18. Implement a Thread-Safe Memoizer

Cache the result of expensive calculations.

### Requirements

- Only one calculation should run for the same key.
- Concurrent callers should receive the same result.
- Failed calculations should not corrupt the cache.
- Use suitable concurrent utilities.
- Avoid holding a global lock during expensive computation.