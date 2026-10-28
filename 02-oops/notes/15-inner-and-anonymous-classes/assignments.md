# Inner and Anonymous Classes Assignments

## Coding Questions

### 1. Create a Member Inner Class

Create:

- `University`
- Member inner class `Department`

### Requirements

- Department should access the university name.
- Create a department through a university object.
- Use private outer fields.
- Demonstrate `OuterClass.this`.

---

### 2. Create a Static Nested Builder

Create an immutable `Employee` class with a static nested `Builder`.

### Requirements

- Build employees with required and optional fields.
- Validate values before object creation.
- Do not require an employee object to create the builder.
- Keep the final employee immutable.

---

### 3. Create a Local Inner Class

Create a report-generation method containing a local formatter class.

### Requirements

- Access an effectively final local variable.
- Format report content.
- Attempt to reassign the captured variable and document the compiler error.
- Keep the local class inside the smallest required scope.

---

### 4. Implement a Callback with an Anonymous Class

Create a task executor accepting a callback.

### Requirements

- Notify the caller on success.
- Notify the caller on failure.
- Implement the callback using an anonymous inner class.
- Repeat the implementation using a lambda when possible.

---

### 5. Compare Anonymous Class and Lambda

Implement `Runnable` using:

1. An anonymous inner class
2. A lambda expression

### Requirements

- Print the value of `this` where valid.
- Explain the difference in `this`.
- Explain scope and object-creation differences.

---

### 6. Extend an Abstract Class Anonymously

Create an abstract `DocumentProcessor` containing an abstract `process()` method.

### Requirements

- Create a one-time implementation using an anonymous class.
- Add an instance initializer.
- Do not create a separately named child class.
- Explain when a named implementation would be better.

---

### 7. Prevent an Outer-Object Retention Problem

Create a long-lived helper as a non-static inner class.

### Requirements

- Explain how the helper retains the outer object.
- Refactor it into a static nested class.
- Pass only required data explicitly.
- Compare both designs.

---

### 8. Access Shadowed Variables

Create an outer class and member inner class with fields having the same name.

### Requirements

Access:

- Local variable
- Inner-class field using `this`
- Outer-class field using `OuterClass.this`

Explain each reference.

---

## Interview Questions and Answers

### 1. What types of nested classes exist in Java?

Static nested classes, member inner classes, local inner classes, and anonymous inner classes.

### 2. What is the difference between a nested class and an inner class?

A nested class is any class declared inside another class. An inner class specifically refers to a non-static nested class.

### 3. Does a member inner class require an outer object?

Yes. A member inner-class instance is associated with an instance of the outer class.

### 4. Can an inner class access private outer members?

Yes. A member inner class can access all members of its enclosing outer object.

### 5. Does a static nested class require an outer object?

No. It can be created using the outer class name.

### 6. Can a static nested class directly access outer instance members?

No. It needs an outer-object reference to access instance members.

### 7. What is a local inner class?

It is a class declared inside a method or block and visible only within that scope.

### 8. What is an effectively final variable?

It is a local variable that is assigned once and not reassigned after initialization.

### 9. Why must captured local variables be final or effectively final?

Local variables belong to a method execution, while the inner object may live longer. Capturing an unchanging value prevents inconsistent behavior.

### 10. What is an anonymous inner class?

It is an unnamed class declared and instantiated in one expression for a one-time implementation.

### 11. Can an anonymous class have a constructor?

It cannot declare an explicit constructor because it has no class name, but it may use an instance initializer.

### 12. When can a lambda replace an anonymous class?

A lambda can replace it when the target type is a functional interface and no anonymous-class-specific behavior is required.

### 13. What does `this` represent inside an anonymous class?

It refers to the anonymous-class object.

### 14. What does `this` represent inside a lambda?

It refers to the enclosing instance because a lambda does not introduce a new `this` scope.

### 15. Why can a non-static inner class cause memory retention?

The inner object normally stores an implicit reference to the outer object, keeping the outer object reachable.

### 16. When should a static nested class be preferred?

Use it when the nested type belongs conceptually to the outer class but does not need an outer instance.
