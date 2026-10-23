# Collections and Generics Coding Questions

These questions test collection selection, equality contracts, generics, ordering, and performance.

## 1. Group Employees by Department

Given a list of employees, create a map where:

- The key is the department name.
- The value is the list of employees in that department.

### Requirements

- Preserve employee insertion order.
- Handle employees without a department.
- Do not repeatedly traverse the input list.
- Do not expose mutable internal collections.

---

## 2. Build an Employee Directory

Store and retrieve employees using employee ID.

### Requirements

- Support add, update, delete, and search operations.
- Prevent duplicate employee IDs.
- Return read-only views when exposing data.
- Select an appropriate collection and justify the choice.
- Handle missing employees clearly.

---

## 3. Find the Top K Frequent Elements

Given an integer array, return the `k` most frequent elements.

### Requirements

- Use a map and heap.
- Define deterministic tie-breaking behavior.
- Avoid sorting the complete input unnecessarily.
- Analyze time and space complexity.
- Handle invalid values of `k`.

---

## 4. Implement an LRU Cache

Implement a fixed-capacity Least Recently Used cache.

### Requirements

- Support `get()` and `put()`.
- Both operations should be `O(1)`.
- Evict the least recently used entry.
- Implement one solution using `LinkedHashMap`.
- Explain the HashMap and doubly linked list implementation.

---

## 5. Merge Overlapping Intervals

Given a collection of intervals, merge all overlapping intervals.

### Requirements

- Create an immutable interval model.
- Sort intervals using a comparator.
- Avoid modifying input objects.
- Handle fully overlapping intervals.
- Analyze time and space complexity.

---

## 6. Sort Employees Using Multiple Fields

Sort employees using the following order:

1. Department
2. Salary in descending order
3. Name
4. Employee ID

### Requirements

- Use comparator composition.
- Handle null values explicitly.
- Do not change equality semantics for sorting.
- Keep the sorting logic reusable.
- Ensure deterministic ordering.

---

## 7. Detect Duplicate Custom Objects

Store custom `Employee` objects inside a `HashSet`.

### Requirements

- Define logical equality.
- Override `equals()` and `hashCode()`.
- Demonstrate duplicate prevention.
- Explain hash collisions.
- Explain problems caused by mutating an object after insertion.

---

## 8. Build a Word-Frequency Analyzer

Count word frequencies in a document.

### Requirements

- Ignore case and punctuation.
- Preserve first-occurrence order.
- Return the most frequent words.
- Handle ties consistently.
- Do not repeatedly scan the complete document.

---

## 9. Implement a Generic Stack

Create a generic stack implementation.

### Requirements

- Support `push()`, `pop()`, `peek()`, `size()`, and `isEmpty()`.
- Prevent exposure of internal storage.
- Handle stack underflow.
- Avoid raw types.
- Avoid unnecessary unchecked casts.

---

## 10. Implement a Generic Repository

Create a generic repository contract for entities having identifiers.

### Requirements

- Support save, find by ID, find all, and delete.
- Use bounded type parameters where appropriate.
- Avoid unchecked casts.
- Return a safe result when an entity is unavailable.
- Keep the repository contract independent of storage technology.

---

## 11. Demonstrate PECS

Create generic methods that:

- Copy elements from one collection to another.
- Read numbers from a producer.
- Add integer values to a consumer.

Demonstrate:

```text
Producer Extends, Consumer Super
```

### Requirements

- Use upper-bounded wildcards for producers.
- Use lower-bounded wildcards for consumers.
- Explain why `List<Object>` is not a parent of `List<String>`.
- Avoid raw collections.

---

## 12. Design a Priority-Based Task Scheduler

Store and process tasks with different priorities.

### Requirements

- Higher-priority tasks must execute first.
- Equal-priority tasks must maintain insertion order.
- Use `PriorityQueue`.
- Keep comparator logic deterministic.
- Prevent task priority changes after insertion.

---

## 13. Find Common Elements Between Collections

Find common elements between two large collections.

### Requirements

- Preserve order from the first collection.
- Remove duplicate results.
- Use an efficient lookup collection.
- Handle null values consistently.
- Analyze time and space complexity.

---

## 14. Implement a Multimap

Implement a generic structure where one key can contain multiple values.

### Requirements

- Support adding and removing values.
- Remove a key when its value collection becomes empty.
- Do not expose internal mutable collections.
- Decide whether duplicate values should be allowed.
- Support retrieving all values safely.

---

## 15. Implement a Frequency-Based Sort

Sort array values according to their frequency.

### Example

```text
Input:  [4, 5, 6, 5, 4, 3]
Output: [4, 4, 5, 5, 3, 6]
```

### Requirements

- Higher-frequency values should appear first.
- Preserve first-occurrence order when frequencies are equal.
- Use appropriate map implementations.
- Explain the complexity.

---

## 16. Build an Inverted Index

Given multiple documents, create an index mapping each word to the documents containing that word.

### Requirements

- Ignore case and punctuation.
- Do not store duplicate document IDs for the same word.
- Support searching by word.
- Return results in deterministic order.
- Choose appropriate generic collection types.

---

## 17. Implement a Bounded Generic Method

Create a generic method that finds the maximum element in a collection.

### Requirements

- Support types implementing `Comparable`.
- Reject empty collections.
- Handle null elements explicitly.
- Use a bounded type parameter.
- Avoid raw types.

---

## 18. Compare Collection Behavior

Write a program demonstrating differences between:

- `ArrayList` and `LinkedList`
- `HashSet` and `TreeSet`
- `HashMap` and `TreeMap`
- `HashMap` and `ConcurrentHashMap`

### Focus Areas

- Ordering
- Null handling
- Duplicate handling
- Time complexity
- Thread safety
- Appropriate use cases