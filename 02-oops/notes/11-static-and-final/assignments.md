# Static and Final Assignments

## Coding Questions

### 1. Track Created Objects

Create an `Employee` class that tracks the total number of created employee objects.

### Requirements

- Use a private static counter.
- Increment the counter during object construction.
- Provide a static method to read the count.
- Do not allow external code to modify the counter.

---

### 2. Create a Utility Class

Create a `NumberUtility` class containing methods for:

- Checking even numbers
- Checking prime numbers
- Finding the maximum value
- Calculating factorial

### Requirements

- Prevent object creation.
- Keep all methods static.
- Make the class non-extendable.
- Do not store unnecessary mutable static state.

---

### 3. Initialize Static Configuration

Create a configuration class containing:

- Application name
- Maximum retry count
- Environment name

### Requirements

- Use static final fields.
- Initialize one field using a static block.
- Print the initialization order.
- Reject invalid configuration during initialization.

---

### 4. Demonstrate Final References

Create a final reference to a mutable list.

### Requirements

- Add and remove list elements.
- Attempt to assign a different list.
- Explain why object mutation is allowed but reference reassignment is not.

---

### 5. Create an Immutable Class

Create an immutable `EmployeeProfile` containing:

- Employee ID
- Name
- Joining date
- List of skills

### Requirements

- Use private final fields.
- Use defensive copying.
- Do not expose mutable internal state.
- Validate all mandatory fields.
- Do not provide setters.

---

### 6. Demonstrate Static Method Hiding

Create parent and child classes with static methods having the same signature.

### Requirements

- Invoke methods using class names.
- Invoke methods using parent and child references.
- Explain why runtime polymorphism does not apply.
- Avoid calling static methods through objects in the final implementation.

---

### 7. Protect Fixed Behavior

Create a payment class containing a final validation method.

### Requirements

- Allow child classes to implement payment processing.
- Prevent child classes from changing common validation behavior.
- Demonstrate that overriding the final method causes a compilation error.

---

## Interview Questions and Answers

### 1. What does the static keyword mean?

A static member belongs to the class rather than individual objects.

### 2. Can a static method access an instance variable directly?

No. It must use an object reference because instance variables belong to objects.

### 3. Can `this` or `super` be used in a static method?

No. A static method has no current object.

### 4. When does a static block execute?

It executes when the JVM initializes the class, generally once per class loader.

### 5. Can static methods be overridden?

No. Static methods are hidden and resolved using the reference or class type.

### 6. What is a blank final variable?

It is a final variable declared without an initial value and assigned exactly once later, usually in a constructor.

### 7. Does a final reference make an object immutable?

No. The reference cannot be reassigned, but the referenced object may still be mutable.

### 8. What is the difference between a final method and a final class?

A final method cannot be overridden. A final class cannot be extended.

### 9. Can a final class contain mutable state?

Yes. Declaring a class final only prevents inheritance; it does not guarantee immutability.

### 10. What is a static nested class?

It is a nested class that does not require an instance of the outer class.

### 11. Why should mutable static variables be avoided?

They create global shared state, increase coupling, complicate testing, and can cause concurrency problems.

### 12. What is the difference between static final and final?

A final instance field belongs to each object. A static final field has one class-level value.
