# Inheritance Assignments

## Coding Questions

### 1. Design an Employee Hierarchy

Create:

- `Employee`
- `Developer`
- `Manager`
- `Contractor`

### Requirements

- Place common state and behavior in the parent class.
- Override work behavior where required.
- Avoid accessing parent state directly when behavior is more suitable.
- Demonstrate runtime substitution.

---

### 2. Demonstrate Constructor Execution Order

Create a three-level hierarchy:

```text
Person -> Employee -> Developer
```

### Requirements

- Add constructors at every level.
- Use `super()` explicitly.
- Print constructor execution order.
- Pass required values through the complete hierarchy.

---

### 3. Demonstrate Protected Access

Create parent and child classes:

1. In the same package
2. In different packages

Test access to a protected method.

### Requirements

- Demonstrate valid subclass access.
- Demonstrate invalid access through an arbitrary parent reference.
- Prefer a protected method over a protected field.

---

### 4. Demonstrate Types of Inheritance

Create concise examples of:

- Single inheritance
- Multilevel inheritance
- Hierarchical inheritance
- Multiple inheritance using interfaces

Do not duplicate unnecessary business logic.

---

### 5. Refactor Inheritance into Composition

A `Car` class extends an `Engine` class only to reuse engine methods.

Refactor the design using composition.

### Requirements

- Inject the engine through a constructor.
- Allow different engine implementations.
- Explain why `Car IS-A Engine` is incorrect.

---

### 6. Demonstrate Field Hiding

Create parent and child classes containing fields with the same name.

### Requirements

- Access the field through parent and child references.
- Compare the behavior with overridden methods.
- Explain why field hiding is not runtime polymorphism.

---

### 7. Validate Substitutability

Create a hierarchy where a child class changes expected parent behavior and breaks calling code.

Refactor the design to restore substitutability using:

- Better abstractions
- Composition
- Separate interfaces

---

## Interview Questions and Answers

### 1. What is inheritance?

Inheritance allows a child class to acquire and extend accessible behavior from a parent class.

### 2. Which relationship does inheritance represent?

Inheritance represents an IS-A relationship.

### 3. Which inheritance types does Java support with classes?

Java supports single, multilevel, and hierarchical class inheritance.

### 4. Why does Java not support multiple class inheritance?

Multiple parent implementations can create ambiguity, including conflicts such as the diamond problem.

### 5. Are constructors inherited?

No. A child constructor invokes a parent constructor but does not inherit it.

### 6. Are private members inherited?

Private members are part of the parent portion of the child object but are not directly accessible in the child class.

### 7. What does the `super` keyword represent?

It provides access to the immediate parent-class constructor and accessible hidden or overridden members.

### 8. What is the difference between method overriding and field hiding?

Overridden instance methods use runtime object type. Hidden fields are selected using the reference type.

### 9. What is protected access?

A protected member is accessible within the same package and through inheritance in subclasses outside the package, subject to reference-access rules.

### 10. When should composition be preferred over inheritance?

Use composition when the relationship is HAS-A, behavior should be replaceable, or inheritance exists only for code reuse.

### 11. What is the fragile base-class problem?

A change in a base class may unintentionally break or alter child-class behavior because children are tightly coupled to the parent implementation.

### 12. What is the root class of Java's class hierarchy?

`java.lang.Object` is the root class of all Java classes.
