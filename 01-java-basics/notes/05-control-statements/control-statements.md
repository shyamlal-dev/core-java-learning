# Control Statements

Control statements determine the flow of program execution.

## Conditional Statements

### `if`

```java
if (age >= 18) {
    System.out.println("Eligible");
}
```

### `if-else`

```java
if (balance >= amount) {
    withdraw();
} else {
    rejectTransaction();
}
```

### `else-if`

```java
if (score >= 90) {
    grade = "A";
} else if (score >= 75) {
    grade = "B";
} else {
    grade = "C";
}
```

Avoid long conditional chains when polymorphism, maps, or rule objects communicate the logic better.

## `switch`

### Traditional Switch

```java
switch (status) {
    case "NEW":
        processNew();
        break;
    case "DONE":
        processCompleted();
        break;
    default:
        handleUnknown();
}
```

Missing `break` causes fall-through.

### Switch Expression

```java
String message = switch (status) {
    case "NEW" -> "New order";
    case "DONE" -> "Completed order";
    default -> "Unknown order";
};
```

A switch expression:

- Can return a value
- Avoids accidental fall-through with arrow labels
- Is often more concise
- Can use `yield` in a block

```java
int fee = switch (type) {
    case "STANDARD" -> 100;
    case "PREMIUM" -> {
        int baseFee = 150;
        yield baseFee + 50;
    }
    default -> 0;
};
```

## Loops

### `for`

Use when the number of iterations is known or index access is required.

```java
for (int index = 0; index < numbers.length; index++) {
    System.out.println(numbers[index]);
}
```

### Enhanced `for`

Use for simple traversal when an index is unnecessary.

```java
for (int number : numbers) {
    System.out.println(number);
}
```

### `while`

Use when repetition depends on a condition.

```java
while (attempts < maxAttempts) {
    attempts++;
}
```

### `do-while`

Executes the body at least once.

```java
do {
    readInput();
} while (shouldContinue());
```

## Jump Statements

### `break`

Terminates a loop or switch.

### `continue`

Skips the current iteration.

### `return`

Ends method execution and optionally returns a value.

## Labeled Statements

A label can control an outer loop.

```java
outer:
for (int row = 0; row < matrix.length; row++) {
    for (int column = 0; column < matrix[row].length; column++) {
        if (matrix[row][column] == target) {
            break outer;
        }
    }
}
```

Use labels sparingly because they may reduce readability.

## Guard Clauses

Guard clauses handle invalid or exceptional conditions early.

```java
void withdraw(Account account, double amount) {
    if (account == null) {
        throw new IllegalArgumentException("Account is required");
    }

    if (amount <= 0) {
        throw new IllegalArgumentException("Amount must be positive");
    }

    // Main logic
}
```

Guard clauses reduce nesting and keep the main flow readable.

## Common Problems

- Infinite loops
- Missing `break` in traditional switch
- Off-by-one errors
- Deeply nested conditions
- Modifying a collection during enhanced-for iteration
- Using loops where a direct calculation is clearer

## Summary

- Use `if` for flexible boolean conditions.
- Use `switch` for a limited set of discrete values.
- Select loops based on iteration requirements.
- Prefer guard clauses over deep nesting.
- Use `break`, `continue`, and labels carefully.