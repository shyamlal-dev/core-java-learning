# Java 8 Coding Questions

These questions focus on lambda expressions, functional interfaces, method references, Optional, and Stream API.

## 1. Group Employees by Department

Using streams, group employees by department.

Additionally calculate:

- Employee count per department
- Highest-paid employee per department
- Average salary per department

### Requirements

- Handle employees without a department.
- Avoid repeated traversal where possible.
- Return deterministic results.
- Do not modify the source list.

---

## 2. Find the Second-Highest Salary

Find the second-highest distinct employee salary.

### Requirements

- Handle duplicate salaries.
- Return an empty result when unavailable.
- Do not access an `Optional` unsafely.
- Define behavior for null employee values.
- Explain the complexity.

---

## 3. Partition Numbers

Partition a list of integers into:

- Even and odd numbers
- Prime and non-prime numbers
- Positive and non-positive numbers

### Requirements

- Use appropriate collectors.
- Keep prime-number logic separate.
- Handle null values explicitly.
- Do not modify the input list.

---

## 4. Build a Word-Frequency Map

Given a list of sentences:

- Normalize words.
- Remove punctuation.
- Count occurrences.
- Sort by frequency in descending order.
- Use alphabetical order as the tie-breaker.

### Requirements

- Ignore empty words.
- Handle null sentences.
- Return deterministic output.
- Avoid external mutable state.

---

## 5. Find Duplicate Elements Using Streams

Find duplicate values in a list.

### Requirements

- Return each duplicate only once.
- Preserve encounter order.
- Avoid external mutable state where possible.
- Handle null values explicitly.
- Do not modify the input list.

---

## 6. Flatten Nested Collections

Convert a nested collection into one list using `flatMap()`.

### Requirements

- Remove duplicates.
- Sort the values.
- Ignore null nested collections.
- Return an unmodifiable result.
- Avoid nested loops.

---

## 7. Create a Custom Functional Interface

Create a functional interface representing a checked operation.

### Requirements

- Execute the operation using a lambda.
- Handle checked exceptions cleanly.
- Avoid silently hiding failures.
- Explain when a standard functional interface should be preferred.
- Keep the interface focused on one responsibility.

---

## 8. Compose Functions

Create reusable functions for:

- Trimming input
- Converting input to lowercase
- Removing special characters
- Validating minimum length

### Requirements

- Combine the functions into a processing pipeline.
- Keep individual functions independently testable.
- Define behavior for null input.
- Avoid modifying external state.

---

## 9. Process Transactions

Given transaction records:

- Filter successful transactions.
- Group transactions by customer.
- Calculate total amount per customer.
- Find the highest-value transaction.
- Return the top three customers by total amount.

### Requirements

- Use `BigDecimal` for monetary values.
- Define tie-breaking behavior.
- Handle empty inputs safely.
- Do not repeatedly traverse the source unnecessarily.

---

## 10. Use Optional Correctly

Build a chain to retrieve:

```text
Employee -> Department -> Manager -> Email
```

### Requirements

- Avoid nested null checks.
- Do not use `Optional` as an entity field.
- Return a default value only when no email exists.
- Do not call `get()` without checking availability.
- Avoid using `Optional` for method parameters.

---

## 11. Implement a Custom Collector

Create a collector that joins normalized strings using a delimiter.

### Requirements

- Implement supplier, accumulator, combiner, and finisher correctly.
- Consider parallel stream execution.
- Avoid global mutable state.
- Define collector characteristics carefully.
- Handle null and blank values.

---

## 12. Compare Sequential and Parallel Streams

Process a large collection using sequential and parallel streams.

### Requirements

- Use an associative operation.
- Avoid shared mutable state.
- Verify that both approaches produce the same result.
- Measure execution carefully.
- Explain why parallel execution is not always faster.

---

## 13. Find Employees with Duplicate Names

Given a list of employees, find names shared by multiple employees.

### Requirements

- Ignore case while comparing names.
- Group employee records by normalized name.
- Exclude names occurring only once.
- Preserve employee encounter order.
- Handle null and blank names.

---

## 14. Convert a List into a Map

Convert a list of employees into a map where employee ID is the key.

### Requirements

- Handle duplicate employee IDs.
- Define a merge strategy.
- Preserve insertion order.
- Avoid accidental data loss.
- Reject or handle null IDs explicitly.

---

## 15. Find the Longest String

Find the longest string in a collection.

### Requirements

- Return an empty result for an empty collection.
- Define tie-breaking behavior.
- Ignore null values.
- Implement using both `reduce()` and `max()`.
- Compare readability of both approaches.

---

## 16. Process Nested Order Data

Given customers containing orders and order items:

- Flatten all orders.
- Calculate total spending per customer.
- Find the most frequently purchased product.
- Find the highest-value order.
- Group products by category.

### Requirements

- Use streams without making the pipeline unreadable.
- Use helper methods for complex logic.
- Handle customers without orders.
- Use `BigDecimal` for amounts.

---

## 17. Find the First Non-Repeating Character

Find the first non-repeating character in a string using streams.

### Requirements

- Preserve character order.
- Handle an empty string.
- Define case sensitivity.
- Avoid repeatedly scanning the string.

---

## 18. Create a Summary Report

Given a list of employees, create a summary containing:

- Minimum salary
- Maximum salary
- Average salary
- Total salary
- Employee count

### Requirements

- Use suitable summary collectors.
- Handle an empty list.
- Use the correct numeric type for salary.
- Keep reporting separate from printing.

---

## 19. Group Anagrams

Group a list of words into anagram groups.

### Example

```text
Input:  ["eat", "tea", "tan", "ate", "nat", "bat"]
Output: [["eat", "tea", "ate"], ["tan", "nat"], ["bat"]]
```

### Requirements

- Preserve word encounter order.
- Ignore case where required.
- Handle duplicate words.
- Use a stable normalized key.

---

## 20. Calculate Department Rankings

Rank employees within each department by salary.

### Requirements

- Group employees by department.
- Sort salary in descending order.
- Use employee ID as the final tie-breaker.
- Return the top three employees from each department.
- Do not modify the original employee list.