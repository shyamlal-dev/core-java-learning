# Data Types and Variables Assignments

## Coding Questions

### 1. Demonstrate Variable Types

Create a class containing:

- One instance variable
- One static variable
- One local variable

Create multiple objects and demonstrate which values are shared and which values belong to individual objects.

---

### 2. Demonstrate Primitive Default Values

Create a class containing all primitive types as instance variables and print their default values.

Then attempt the same with local variables and observe the compiler behavior.

---

### 3. Safe Type Conversion

Create a method that converts a `long` value to `int`.

### Requirements

- Validate whether the value fits inside the `int` range.
- Do not silently allow overflow.
- Return or throw a clear result when conversion is unsafe.

---

### 4. Calculate Financial Amounts

Calculate the total price of multiple products including tax.

### Requirements

- First implement using `double`.
- Implement another version using `BigDecimal`.
- Compare the results.
- Avoid constructing `BigDecimal` directly from a `double`.

---

### 5. Demonstrate Integer Overflow

Create a program that adds one to `Integer.MAX_VALUE`.

### Requirements

- Print the result.
- Explain why overflow occurs.
- Use `Math.addExact()` to detect the overflow.

---

### 6. Character Processing

Create a program that receives a character and determines whether it is:

- An uppercase letter
- A lowercase letter
- A digit
- Another character

Use Java character utility methods instead of hard-coded ASCII ranges.

---

### 7. Swap Two Integer Values

Swap two integer values using:

1. A temporary variable
2. Arithmetic operations

Explain which implementation is safer and why.

---

## Interview Questions and Answers

### 1. What is the difference between primitive and reference types?

A primitive variable stores its value directly. A reference variable stores a reference used to access an object.

### 2. Do local variables receive default values?

No. A local variable must be definitely assigned before it is read.

### 3. Where are variables stored in Java?

Storage depends on the variable and JVM implementation. Local primitive values and references are typically part of stack frames, while objects are generally allocated on the heap. The JVM may optimize allocation.

### 4. Why does adding two byte values produce an int?

Java applies binary numeric promotion. Values of `byte`, `short`, and `char` are promoted to `int` during most arithmetic operations.

### 5. What is the difference between widening and narrowing?

Widening converts a smaller compatible type to a larger type automatically. Narrowing requires an explicit cast and may lose data.

### 6. Why should double generally not be used for money?

Binary floating-point values cannot represent many decimal fractions exactly. `BigDecimal` provides explicit decimal precision and rounding control.

### 7. Is `var` dynamically typed?

No. The compiler infers the type at compile time, and the variable remains statically typed.

### 8. Can a boolean be converted to int in Java?

No. Java does not provide numeric conversion between `boolean` and integer types.