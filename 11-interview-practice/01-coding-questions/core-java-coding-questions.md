# Core Java Combined Coding Questions

These are integrated SDE-level problems combining multiple Core Java concepts. Attempt these problems after completing the topic-specific question sets.

## 1. Build an In-Memory Employee Management System

Support:

- Add, update, remove, and search employees
- Department-wise grouping
- Salary-based sorting
- Duplicate prevention
- Custom exception handling
- Thread-safe access

### Requirements

- Use immutable or safely encapsulated employee objects.
- Define employee equality correctly.
- Do not expose mutable internal collections.
- Support concurrent reads and updates.
- Keep storage and business logic separate.

### Concepts Covered

- OOP
- Collections
- Equality contract
- Exception handling
- Concurrency

---

## 2. Build an In-Memory LRU Cache

Support:

- Generic key-value storage
- Fixed capacity
- LRU eviction
- Entry expiration
- Thread-safe access
- Cache hit and miss statistics

### Requirements

- `get()` and `put()` should be efficient.
- Expired entries must not be returned.
- Avoid exposing internal mutable values.
- Allow cache configuration during construction.
- Prevent duplicate calculations where appropriate.

### Concepts Covered

- Generics
- Collections
- Concurrency
- Object design
- Date-Time API

---

## 3. Build a Transaction Processing System

Read transactions from a file and generate:

- Successful transaction report
- Failed transaction report
- Customer-wise totals
- Highest-value transactions
- Failure reasons

### Requirements

- Invalid records must not stop complete processing.
- Use immutable transaction objects.
- Process large files efficiently.
- Keep parsing, validation, processing, and reporting separate.
- Use `BigDecimal` for monetary values.

### Concepts Covered

- File handling
- Exception handling
- Collections
- Stream API
- Immutable objects

---

## 4. Build a Task Scheduling System

Support:

- Task priority
- Delayed execution
- Concurrent task processing
- Retry for temporary failures
- Task cancellation
- Graceful shutdown

### Requirements

- Equal-priority tasks must follow insertion order.
- Failed tasks must record failure information.
- Avoid creating one thread for every task.
- Support configurable retry policies.
- Prevent invalid task status transitions.

### Concepts Covered

- OOP
- PriorityQueue
- Executor framework
- CompletableFuture
- Exception handling

---

## 5. Build an Order Management System

Support:

- Order creation
- Multiple order items
- Inventory validation
- Discount calculation
- Payment strategies
- Order status transitions
- Customer notifications

### Requirements

- Prevent invalid status transitions.
- Support multiple payment implementations.
- Support multiple notification implementations.
- Avoid creating a God class.
- Keep business rules independently testable.
- Use suitable design patterns.

### Concepts Covered

- OOP
- SOLID principles
- Collections
- Custom exceptions
- Enums
- Functional interfaces

---

## 6. Build a Log Analyzer

Read application logs and produce:

- Error count by type
- Most frequent errors
- Errors grouped by hour
- Affected service names
- Top recurring messages

### Requirements

- Parse valid and malformed log entries.
- Continue processing after invalid entries.
- Handle large files efficiently.
- Generate a clear summary report.
- Keep parsing separate from analysis.

### Concepts Covered

- File handling
- Regular expressions
- Collections
- Stream API
- Date-Time API

---

## 7. Build a Concurrent Inventory System

Allow multiple threads to reserve and release inventory.

### Requirements

- Inventory must never become negative.
- Updates must be atomic.
- Avoid global locking where possible.
- Detect insufficient inventory.
- Record every inventory movement.
- Support safe concurrent reads.

### Concepts Covered

- OOP
- Concurrent collections
- Locks
- Atomic operations
- Exception handling

---

## 8. Build a Mini JDBC Repository Application

Create a repository-based application for employees or products.

### Requirements

- Implement CRUD operations.
- Add transaction handling.
- Support batch insertion.
- Add pagination.
- Use connection pooling.
- Translate database exceptions.
- Implement clean domain mapping.
- Support optimistic locking.

### Concepts Covered

- JDBC
- Generics
- OOP
- Exception handling
- Resource management

---

## 9. Build a Library Management Application

Support:

- Books and physical book copies
- Member registration
- Book issue and return
- Due-date calculation
- Fine calculation
- Book availability search
- Concurrent issue requests

### Requirements

- Distinguish book details from physical copies.
- Prevent one copy from being issued twice.
- Keep fine calculation configurable.
- Maintain borrowing history.
- Use suitable collections.
- Handle concurrent requests safely.

### Concepts Covered

- OOP
- Collections
- Concurrency
- Exception handling
- Date-Time API

---

## 10. Build a Configurable Notification Platform

Support:

- Email notifications
- SMS notifications
- Push notifications
- Retry policies
- Notification templates
- Asynchronous delivery
- Delivery status tracking

### Requirements

- Adding a channel must not change existing channels.
- Failed notifications must follow configurable retry rules.
- Keep template creation separate from delivery.
- Process notifications using an executor.
- Store clear delivery results.

### Concepts Covered

- Interfaces
- SOLID principles
- Strategy pattern
- Executor framework
- Exception handling

---

## 11. Build a Concurrent Booking System

Create a booking system for limited seats.

### Requirements

- Multiple customers may attempt booking concurrently.
- The same seat must never be booked twice.
- Support booking cancellation.
- Track booking history.
- Use custom exceptions for unavailable seats.
- Avoid locking the complete system unnecessarily.

### Concepts Covered

- OOP
- Collections
- Concurrency
- Locks
- Exception handling

---

## 12. Build a Rule-Based Fraud Detection Engine

Evaluate transactions using multiple fraud rules.

### Example Rules

- Unusually high transaction amount
- Multiple transactions within a short time
- Transaction from an unexpected location
- Repeated failed payments

### Requirements

- Rules must be independently testable.
- New rules must be easy to add.
- Return all triggered rules.
- Process large transaction collections efficiently.
- Avoid a long conditional chain.

### Concepts Covered

- OOP
- Strategy pattern
- Collections
- Stream API
- Date-Time API

---

## Recommended Implementation Order

1. In-Memory Employee Management System
2. Transaction Processing System
3. In-Memory LRU Cache
4. Log Analyzer
5. Order Management System
6. Concurrent Inventory System
7. Task Scheduling System
8. Library Management Application
9. Configurable Notification Platform
10. Concurrent Booking System
11. JDBC Repository Application
12. Fraud Detection Engine

## Implementation Guidelines

For every project:

1. Start with domain modelling.
2. Define interfaces and responsibilities.
3. Implement the simplest correct version.
4. Handle invalid inputs and edge cases.
5. Add thread safety only where required.
6. Refactor duplicated or tightly coupled logic.
7. Write tests for important business rules.
8. Document major design decisions.