# Methods Assignments

## Coding Questions

### 1. Create an Overloaded Calculator

Create overloaded methods for adding:

- Two integers
- Three integers
- Two decimal numbers
- An array of integers

### Requirements

- Avoid duplicated calculation logic where practical.
- Demonstrate compile-time method selection.

---

### 2. Demonstrate Pass-by-Value

Create examples showing:

1. Passing a primitive variable
2. Passing an object reference
3. Reassigning an object parameter

Explain why object state may change while the caller's reference cannot be replaced by the method.

---

### 3. Build a Validation Utility

Create focused methods for validating:

- Name
- Email
- Age
- Salary

### Requirements

- Each method should have one responsibility.
- Return meaningful validation results.
- Avoid one large method with deeply nested conditions.

---

### 4. Implement a Generic Calculation Flow

Create methods for:

- Reading numbers
- Validating numbers
- Calculating average
- Finding minimum and maximum
- Formatting the result

Keep input/output logic separate from calculations.

---

### 5. Implement Varargs Operations

Create methods using varargs to:

- Calculate a sum
- Find a maximum
- Calculate an average

### Requirements

- Handle zero arguments.
- Define behavior for invalid input.
- Avoid unnecessary array copying.

---

### 6. Implement Recursive and Iterative Solutions

Implement both recursive and iterative versions of:

- Factorial
- Fibonacci
- Sum of digits

Compare readability, complexity, and stack usage.

---

### 7. Refactor a Long Method

Refactor a method that:

- Validates an order
- Calculates the subtotal
- Applies a discount
- Adds tax
- Prints a receipt

Extract focused methods with meaningful names.

---

## Interview Questions and Answers

### 1. Is Java pass-by-reference?

No. Java always passes arguments by value. For objects, the copied value is the object reference.

### 2. What is method overloading?

Method overloading defines multiple methods with the same name but different parameter lists.

### 3. Can methods be overloaded using only different return types?

No. Return type alone is not part of method overload resolution.

### 4. What is the difference between a parameter and an argument?

A parameter is declared in a method signature. An argument is the actual value passed during invocation.

### 5. How are varargs handled internally?

A varargs parameter is treated as an array by the compiler.

### 6. Can a static method be overridden?

Static methods are hidden rather than overridden because method selection is based on the reference type, not runtime object polymorphism.

### 7. What causes StackOverflowError in recursion?

It occurs when method calls consume the available thread stack, commonly because of very deep recursion or a missing base condition.

### 8. What makes a method easy to maintain?

A maintainable method usually has one clear responsibility, a meaningful name, limited parameters, predictable side effects, and manageable complexity.