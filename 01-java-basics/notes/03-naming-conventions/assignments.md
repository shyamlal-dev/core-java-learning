# Naming Conventions Assignments

## Coding Questions

### 1. Refactor Poor Identifiers

Refactor the following code using clear Java naming conventions:

```java
class emp_mgr {
    int EC;
    final int max = 10;

    void get(E e) {
        int x = e.sal;
    }
}
```

### Requirements

- Rename the class.
- Rename fields, methods, parameters, and local variables.
- Correct the constant declaration.
- Explain every important rename.

---

### 2. Design Names for an Order Domain

Create suitable names for classes, methods, variables, and enums required for:

- Creating an order
- Adding order items
- Calculating totals
- Processing payment
- Cancelling an order
- Checking order status

Focus on names only. Do not implement complete business logic.

---

### 3. Create a Boolean Validation API

Create an `Employee` validation utility with methods for checking:

- Whether the employee is active
- Whether the employee can receive a bonus
- Whether the employee has management access
- Whether the employee profile is complete

Use readable boolean method names.

---

### 4. Remove Misleading Names

Refactor a program where:

- A `List` is named `employeeSet`
- A saving method is named `getEmployee`
- A total amount is named `temp`
- A boolean variable is named `status`

Choose names that communicate actual intent.

---

### 5. Create a Generic Repository Contract

Design a generic repository interface using appropriate generic type parameter names.

The repository should support:

- Save
- Find by ID
- Find all
- Delete by ID

---

## Interview Questions and Answers

### 1. Are Java naming conventions enforced by the compiler?

Generally, no. However, a public top-level class name must match its source file name.

### 2. Why are naming conventions important?

They reduce cognitive load, improve code reviews, communicate intent, and make a codebase consistent.

### 3. How should boolean methods be named?

Names commonly begin with `is`, `has`, or `can`, such as `isActive()` or `hasPermission()`.

### 4. How should constants be named?

True constants are generally written using uppercase letters separated by underscores, such as `MAX_RETRY_COUNT`.

### 5. Should abbreviations be used in identifiers?

Only when they are widely understood in the project domain. Unclear abbreviations reduce readability.

### 6. What is a misleading identifier?

A misleading identifier suggests behavior or a type different from the actual implementation, such as naming a list `employeeSet`.

### 7. Can good naming replace every comment?

No. Good names reduce unnecessary comments, but comments may still be required for business decisions, constraints, and non-obvious reasoning.