# JDBC Coding Questions

These questions test safe database access, transaction management, resource handling, and repository design.

## 1. Implement Employee CRUD Operations

Create JDBC operations to:

- Insert an employee
- Find an employee by ID
- Update employee details
- Delete an employee
- Retrieve all employees

### Requirements

- Use `PreparedStatement`.
- Use try-with-resources.
- Do not expose JDBC objects outside the repository.
- Return a safe result when an employee is unavailable.
- Keep row mapping separate from SQL execution.

---

## 2. Prevent SQL Injection

Create an employee search or login operation.

### Requirements

- Demonstrate the risk of string-concatenated SQL.
- Replace concatenation with `PreparedStatement`.
- Validate allowed sorting columns separately.
- Never log passwords or sensitive values.
- Do not accept raw SQL fragments from callers.

---

## 3. Implement a Money Transfer Transaction

Transfer money between two bank accounts.

### Requirements

- Disable auto-commit.
- Debit and credit must execute as one transaction.
- Roll back on failure.
- Restore connection state where required.
- Handle insufficient balance safely.
- Prevent partial updates.

---

## 4. Implement JDBC Batch Processing

Insert a large collection of employees.

### Requirements

- Use JDBC batch processing.
- Process records in configurable batch sizes.
- Handle partial failures.
- Compare batch insertion with individual insertion.
- Clear batches at appropriate intervals.

---

## 5. Map ResultSet to Domain Objects

Convert database rows into immutable employee objects.

### Requirements

- Keep row-mapping logic separate.
- Handle nullable columns.
- Avoid fragile column-index access where practical.
- Do not return partially initialized objects.
- Convert SQL-specific types appropriately.

---

## 6. Implement Pagination

Retrieve employee records page by page.

### Requirements

- Use deterministic ordering.
- Validate page number and page size.
- Implement using `LIMIT` and `OFFSET`.
- Explain the limitation of large offsets.
- Design a keyset pagination alternative.

---

## 7. Call a Stored Procedure

Use `CallableStatement` to call a stored procedure.

### Requirements

- Pass input parameters.
- Register and retrieve output parameters.
- Handle SQL exceptions properly.
- Keep stored-procedure details inside the repository layer.
- Close all resources safely.

---

## 8. Use a Connection Pool

Refactor direct connection creation to use `DataSource`.

### Requirements

- Acquire and close connections correctly.
- Understand pooled connection closing behavior.
- Do not keep connections in static mutable fields.
- Configure sensible pool size and timeout values.
- Prevent connection leaks.

---

## 9. Implement Optimistic Locking

Prevent lost updates when two clients update the same record.

### Requirements

- Add a version column.
- Include the current version in the update condition.
- Increment the version after successful updates.
- Detect when no row is updated.
- Return a clear concurrency failure.

---

## 10. Build a Transactional Order Operation

Create an operation that:

1. Creates an order.
2. Saves order items.
3. Updates inventory.
4. Records payment status.

### Requirements

- Execute related steps inside one transaction.
- Roll back incomplete operations.
- Keep SQL logic separate from business orchestration.
- Preserve the original failure cause.
- Restore connection configuration safely.

---

## 11. Implement a Generic Row Mapper

Create a reusable functional interface that maps a `ResultSet` row to a domain object.

### Requirements

- Use generics.
- Avoid duplicated mapping loops.
- Handle `SQLException` correctly.
- Keep domain-specific mapping outside generic JDBC utilities.
- Do not expose `ResultSet` beyond the mapping callback.

---

## 12. Handle Generated Keys

Insert an order and retrieve its generated ID.

### Requirements

- Request generated keys explicitly.
- Validate that a key is returned.
- Use the generated ID when inserting order items.
- Keep the operation transactional.
- Handle drivers returning unexpected key results.

---

## 13. Implement Search with Dynamic Filters

Search employees using optional filters:

- Name
- Department
- Minimum salary
- Maximum salary
- Joining date

### Requirements

- Build SQL safely.
- Use parameters for user-provided values.
- Do not concatenate raw input.
- Keep parameter order consistent.
- Avoid unnecessary conditions.

---

## 14. Create a JDBC Repository Layer

Create a repository for a product or employee domain.

### Requirements

- Separate repository interfaces from JDBC implementations.
- Translate SQL exceptions into application-level exceptions.
- Keep connection management centralized.
- Make repository methods independently testable.
- Avoid storing business logic inside repository classes.

---

## 15. Handle Transaction Savepoints

Process an order containing multiple items.

### Requirements

- Create a savepoint before processing optional items.
- Roll back to the savepoint when an optional item fails.
- Preserve mandatory operations.
- Commit only when the required operations succeed.
- Release resources safely.

---

## 16. Detect and Prevent Connection Leaks

Create a program that performs repeated database operations.

### Requirements

- Demonstrate how a connection leak can occur.
- Correct the problem using try-with-resources.
- Ensure statements and result sets are closed.
- Test behavior when an exception occurs.
- Explain the impact on the connection pool.

---

## 17. Handle Database Null Values

Read and write nullable employee fields.

### Requirements

- Use `setNull()` where appropriate.
- Distinguish SQL `NULL` from Java primitive defaults.
- Use `wasNull()` when required.
- Map nullable fields safely.
- Avoid incorrectly converting `NULL` into zero or false.

---

## 18. Implement a Transaction Retry

Retry a database transaction after a temporary failure.

### Requirements

- Retry only known transient failures.
- Use a limited retry count.
- Roll back before every retry.
- Do not retry validation or constraint failures.
- Preserve the final cause when all attempts fail.