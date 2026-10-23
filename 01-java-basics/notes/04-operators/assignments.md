# Operators Assignments

## Coding Questions

### 1. Check Even or Odd Using Bitwise Operator

Determine whether an integer is even or odd without using the remainder operator.

### Requirements

- Support positive and negative numbers.
- Explain how the least significant bit is used.

---

### 2. Swap Numbers Using XOR

Swap two integer values using XOR.

### Requirements

- Do not use a temporary variable.
- Explain why this approach should generally not replace the readable temporary-variable approach.
- Consider what happens when both references represent the same array position.

---

### 3. Check a Power of Two

Determine whether a positive integer is a power of two using bitwise operations.

### Requirements

- Handle zero and negative numbers.
- Target time complexity: `O(1)`.

---

### 4. Count Set Bits

Count the number of `1` bits in an integer.

### Requirements

- Implement a basic bit-by-bit solution.
- Implement Brian Kernighan's algorithm.
- Compare the number of iterations.

---

### 5. Find the Unique Element

An array contains every number twice except one number. Find the unique number.

### Requirements

- Use XOR.
- Target time complexity: `O(n)`.
- Target space complexity: `O(1)`.

---

### 6. Demonstrate Short-Circuit Evaluation

Create a safe condition that accesses an object only when the reference is not null.

Then demonstrate the risk of using `&` instead of `&&` for the same condition.

---

### 7. Build a Permission System

Represent the following permissions using bit flags:

- Read
- Write
- Update
- Delete

### Requirements

- Add a permission.
- Remove a permission.
- Check whether a permission exists.
- Combine multiple permissions.

---

## Interview Questions and Answers

### 1. What is the difference between `&&` and `&`?

For boolean operands, both perform logical AND, but `&&` short-circuits while `&` always evaluates both operands. `&` also performs bitwise AND on integral values.

### 2. What is the difference between `==` and `equals()`?

For references, `==` checks whether two references point to the same object. `equals()` is used for logical equality when appropriately overridden.

### 3. What is the difference between `>>` and `>>>`?

`>>` preserves the sign bit. `>>>` shifts zeros into the leftmost positions.

### 4. Why does `byteValue += 1` compile but `byteValue = byteValue + 1` not compile?

Arithmetic promotes the operands to `int`. Compound assignment performs an implicit cast back to the left-hand type.

### 5. What is short-circuit evaluation?

It means the right operand of `&&` or `||` is evaluated only when required to determine the result.

### 6. What is the difference between prefix and postfix increment?

Prefix increment updates the value before returning it. Postfix increment returns the current value and then updates it.

### 7. Can integer division throw an exception?

Dividing an integer by zero throws `ArithmeticException`. Floating-point division by zero produces infinity or `NaN`, depending on the operands.