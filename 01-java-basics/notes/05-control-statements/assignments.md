# Control Statements Assignments

## Coding Questions

### 1. FizzBuzz with Clear Rules

Print numbers from `1` to `n`.

- Print `Fizz` for multiples of 3.
- Print `Buzz` for multiples of 5.
- Print `FizzBuzz` for multiples of both.

### Requirements

- Avoid duplicated conditions.
- Validate that `n` is positive.

---

### 2. Find Prime Numbers in a Range

Print all prime numbers between two given numbers.

### Requirements

- Avoid unnecessary divisor checks.
- Handle invalid ranges.
- Move prime checking into a separate method.

---

### 3. Validate a Palindrome Number

Determine whether an integer is a palindrome.

### Requirements

- Do not convert the number to a string.
- Handle negative numbers.
- Avoid overflow while reversing digits.

---

### 4. Search in a Matrix

Find the first occurrence of a target value in a matrix.

### Requirements

- Stop both loops once the value is found.
- Return row and column indexes.
- Handle an empty matrix.
- Implement without using a labelled statement first, then compare with a labelled solution.

---

### 5. Create a Menu-Driven Calculator

Create a menu supporting:

- Addition
- Subtraction
- Multiplication
- Division
- Exit

### Requirements

- Use `switch`.
- Continue until the user chooses exit.
- Handle invalid choices and division by zero.
- Keep calculation logic in separate methods.

---

### 6. Validate a Password

Validate a password using control statements.

### Rules

- Minimum eight characters
- At least one uppercase letter
- At least one lowercase letter
- At least one digit
- At least one special character

Return all missing requirements instead of stopping at the first failure.

---

### 7. Print Number Patterns

Generate the following pattern for `n = 4`:

```text
1
1 2
1 2 3
1 2 3 4
```

Then generate the reverse pattern.

Focus on correct loop boundaries.

---

## Interview Questions and Answers

### 1. What is the difference between `while` and `do-while`?

`while` checks the condition before execution. `do-while` executes the body once before checking the condition.

### 2. What is fall-through in a switch statement?

In a traditional switch, execution continues into the next case when `break` is omitted.

### 3. What is a switch expression?

A switch expression can return a value and supports arrow labels that avoid accidental fall-through.

### 4. What is the difference between `break`, `continue`, and `return`?

- `break` exits a loop or switch.
- `continue` skips the current loop iteration.
- `return` exits the current method.

### 5. What is an infinite loop?

An infinite loop is a loop whose termination condition never becomes false or is absent.

### 6. What is a guard clause?

A guard clause handles invalid or special conditions early, reducing nesting in the main business logic.

### 7. When should a long if-else chain be refactored?

Refactor when conditions represent separate behaviors or frequently changing rules. Polymorphism, strategy objects, or lookup maps may provide a cleaner design.