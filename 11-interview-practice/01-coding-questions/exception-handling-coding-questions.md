# Exception Handling Coding Questions

These questions test exception design, propagation, translation, recovery, and resource management.

## 1. Implement a Bank Withdrawal Operation

Create a withdrawal operation that may throw:

- `InvalidAmountException`
- `InsufficientBalanceException`
- `AccountBlockedException`

### Requirements

- Create meaningful custom exceptions.
- Do not catch an exception unless it can be handled.
- Keep business exceptions separate from programming errors.
- Add useful and concise error messages.
- Do not expose sensitive account information.

---

## 2. Validate Employee Registration

Validate the following employee fields:

- Name
- Email
- Age
- Salary

### Requirements

- Create appropriate validation exceptions.
- Return all validation failures together where appropriate.
- Do not use exceptions for normal boolean checks unnecessarily.
- Do not expose sensitive values in exception messages.
- Keep validation separate from persistence logic.

---

## 3. Process a File Safely

Read and process a text file line by line.

### Requirements

- Use try-with-resources.
- Handle malformed records separately from file-access failures.
- Continue processing valid records.
- Record the reason for every rejected record.
- Produce a summary of successful and failed records.

---

## 4. Implement Exception Translation

Create repository, service, and controller layers.

### Requirements

- The repository throws a persistence-related exception.
- The service translates it into a business-level exception.
- Preserve the original exception as the cause.
- Do not expose database implementation details to callers.
- Avoid catching and throwing the same exception without adding value.

---

## 5. Implement a Retry Mechanism

Execute an operation that may fail temporarily.

### Requirements

- Retry only retryable exceptions.
- Accept a configurable maximum retry count.
- Add a delay between attempts.
- Immediately propagate non-retryable exceptions.
- Preserve the final failure cause.
- Do not retry validation or programming errors.

---

## 6. Copy a File Using Multiple Resources

Copy data from one file to another using buffered streams.

### Requirements

- Use try-with-resources.
- Ensure both resources are closed correctly.
- Do not manually close resources in `finally`.
- Handle failures from the copy operation.
- Demonstrate suppressed exceptions.

---

## 7. Create a Safe Batch Processor

Process a collection of transactions where individual transactions may fail.

### Requirements

- One invalid transaction must not stop the complete batch.
- Capture the failure reason for each failed transaction.
- Return successful and failed results separately.
- Do not use empty catch blocks.
- Do not silently ignore failures.

---

## 8. Build a Global Error Response

Create a reusable error response containing:

- Error code
- Message
- Timestamp
- Field validation errors

### Requirements

- Separate internal details from client-facing messages.
- Map exception types to meaningful error codes.
- Centralize error-response construction.
- Avoid returning stack traces to clients.
- Keep the response object immutable.

---

## 9. Wrap a Checked Exception

Create a service that loads application configuration from a file.

### Requirements

- Catch the low-level checked exception.
- Wrap it in a meaningful application exception.
- Preserve the original exception as the cause.
- Keep the service method signature meaningful.
- Do not hide the actual reason for failure.

---

## 10. Implement AutoCloseable

Create a custom resource implementing `AutoCloseable`.

### Requirements

- Use the resource with try-with-resources.
- Ensure `close()` is always called.
- Handle failures from both the main operation and `close()`.
- Inspect suppressed exceptions.
- Make repeated closing safe where appropriate.

---

## 11. Validate Method Arguments

Create utility methods that validate arguments and use suitable standard exceptions.

### Consider

- `IllegalArgumentException`
- `IllegalStateException`
- `NullPointerException`
- `IndexOutOfBoundsException`

### Requirements

- Use standard exceptions where they communicate the problem clearly.
- Avoid unnecessary custom exception classes.
- Include meaningful messages.
- Validate arguments before modifying state.

---

## 12. Build a Transactional Operation

Simulate an operation performing:

1. Account debit
2. Account credit
3. Transaction logging

### Requirements

- Roll back completed steps when a later step fails.
- Preserve the original failure.
- Separate recovery logic from error reporting.
- Do not leave the system in a partially updated state.
- Avoid catching overly broad exception types.

---

## 13. Parse User Input Safely

Read and convert user input into:

- Integer
- Decimal value
- Date
- Enum value

### Requirements

- Handle invalid input without terminating the application.
- Return meaningful validation messages.
- Do not use one broad catch block for unrelated failures.
- Keep parsing and business logic separate.

---

## 14. Handle Exceptions in a Multithreaded Task

Execute a collection of tasks using `ExecutorService`.

### Requirements

- Capture exceptions raised by individual tasks.
- Distinguish task failures from interruption.
- Restore the interrupt flag when required.
- Ensure executor shutdown.
- Report successful and failed tasks separately.

---

## 15. Design a Domain Exception Hierarchy

Create exceptions for an order-processing system.

### Include

- Invalid order
- Insufficient inventory
- Payment failure
- Invalid status transition

### Requirements

- Avoid an unnecessarily deep hierarchy.
- Keep checked and unchecked exception choices meaningful.
- Provide error codes where useful.
- Preserve the original cause for infrastructure failures.
- Avoid exposing third-party exceptions to domain callers.