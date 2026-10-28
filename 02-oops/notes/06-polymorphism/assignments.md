# Polymorphism Assignments

## Coding Questions

### 1. Design an Employee Payroll System

Create:

- `Employee`
- `FullTimeEmployee`
- `PartTimeEmployee`
- `ContractEmployee`

### Requirements

- Define a common salary-calculation method.
- Override the method in each employee type.
- Calculate salaries through parent references.
- Do not use `instanceof` or employee-type conditions.

---

### 2. Create a Payment Processor

Support:

- Credit-card payment
- UPI payment
- Bank-transfer payment

### Requirements

- Define a common payment method.
- Use runtime polymorphism.
- Store payment implementations in a collection.
- Process payments without checking concrete types.

---

### 3. Demonstrate Method Overloading

Create overloaded methods for calculating:

- Area of a circle
- Area of a rectangle
- Area of a square

### Requirements

- Use different parameter lists.
- Demonstrate compile-time method selection.
- Explain why return type alone cannot be used for overloading.

---

### 4. Demonstrate Variable Hiding

Create parent and child classes containing:

- A field with the same name
- An overridden instance method

Access both through a parent reference holding a child object.

Explain why the field and method produce different results.

---

### 5. Demonstrate Static Method Hiding

Create parent and child classes containing static methods with the same signature.

### Requirements

- Call the method using parent and child class names.
- Call the method using a parent reference holding a child object.
- Explain why static methods do not support runtime polymorphism.

---

### 6. Demonstrate Private and Final Methods

Create examples showing:

- A private method cannot be overridden.
- A final method cannot be overridden.
- A final class cannot be extended.

Add comments explaining compiler errors where required.

---

### 7. Implement Covariant Return Types

Create:

- `Document`
- `PdfDocument`
- `DocumentFactory`
- `PdfDocumentFactory`

Override a factory method so the child implementation returns `PdfDocument`.

---

### 8. Remove an `instanceof` Chain

A notification service uses `instanceof` to identify email, SMS, and push notifications.

Refactor the code using runtime polymorphism.

### Requirements

- Each notification type should handle its own behavior.
- Adding a new notification type should not modify existing processing code.
- Avoid downcasting.

---

## Interview Questions and Answers

### 1. What is polymorphism?

Polymorphism allows one reference type or contract to represent objects having different implementations.

### 2. What is compile-time polymorphism?

Compile-time polymorphism is method overloading, where the compiler selects a method using the parameter list.

### 3. What is runtime polymorphism?

Runtime polymorphism is method overriding, where the JVM selects the implementation using the actual object type.

### 4. What is dynamic method dispatch?

It is the runtime process of selecting an overridden instance method based on the actual object type.

### 5. Are variables polymorphic?

No. Fields are hidden and resolved using the reference type at compile time.

### 6. Can static methods be overridden?

No. Static methods are hidden because they belong to classes and are selected using the reference type.

### 7. Can private methods be overridden?

No. Private methods are not inherited and are not visible to child classes.

### 8. Can final methods be overridden?

No. A final method fixes its implementation for child classes.

### 9. What is upcasting?

Upcasting stores a child object in a parent reference. It is implicit and enables runtime polymorphism.

### 10. What is downcasting?

Downcasting converts a parent reference into a child reference. An incompatible cast causes `ClassCastException`.

### 11. What is a covariant return type?

It allows an overriding method to return a subtype of the return type declared by the parent method.

### 12. Can methods be overloaded only by changing the return type?

No. Method overloading requires a different parameter list.

### 13. Why is `@Override` recommended?

It allows the compiler to verify that a method correctly overrides an inherited method.

### 14. Does method overloading depend on the runtime object type?

No. Overload resolution happens at compile time using declared argument types.
