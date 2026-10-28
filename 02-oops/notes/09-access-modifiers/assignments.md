# Access Modifiers Assignments

## Coding Questions

### 1. Demonstrate All Access Levels

Create two packages containing parent, child, and unrelated classes.

Test access to:

- Private members
- Package-private members
- Protected members
- Public members

Document which accesses compile and which fail.

---

### 2. Demonstrate Protected Cross-Package Access

Create:

- A public parent class in one package
- A child class in another package

### Requirements

- Access the protected member through inheritance.
- Attempt access using a parent-class object.
- Attempt access using a child-class object.
- Explain the protected-reference restriction.

---

### 3. Control Object Creation

Create a class with:

- Private constructor
- Public static factory method
- Validation before object creation

### Requirements

- Prevent direct construction.
- Return only valid objects.
- Explain why the constructor is private.

---

### 4. Design a Package API

Create a payment package containing:

- Public payment-service interface
- Public payment result
- Package-private validator
- Package-private helper implementation

### Requirements

- Expose only the required API.
- Keep implementation details inside the package.
- Avoid unnecessary public classes.

---

### 5. Demonstrate Visibility in Overriding

Create parent methods with package-private, protected, and public access.

Override them with valid visibility levels.

Also document invalid attempts to reduce visibility.

---

### 6. Refactor Public Fields

A class exposes the following public fields:

- Account number
- Balance
- Account status
- Transaction history

Refactor the class using suitable access modifiers and meaningful operations.

---

## Interview Questions and Answers

### 1. What access modifiers are available in Java?

Java provides private, package-private, protected, and public access levels.

### 2. What is package-private access?

A member without an explicit access modifier is accessible only inside the same package.

### 3. Is package-private the same as protected?

No. Protected also provides controlled access to subclasses outside the package.

### 4. Can a top-level class be private or protected?

No. A top-level class can be public or package-private.

### 5. Can a nested class be private?

Yes. Nested classes may use all access modifiers.

### 6. Can an overriding method reduce visibility?

No. Reducing visibility would violate the parent method's contract.

### 7. Can a private method be overridden?

No. It is not visible or inherited by child classes.

### 8. Is a protected member accessible everywhere inside the same package?

Yes. Within the same package, protected access behaves similarly to package-private access.

### 9. How does protected access work for a subclass in another package?

The subclass can access the protected member through inheritance, subject to restrictions on the reference used.

### 10. Why should the least permissive access level be used?

It reduces coupling, protects implementation details, and limits accidental misuse.

### 11. What is the use of a private constructor?

It controls object creation and is commonly used in utility classes, static factories, and singleton implementations.

### 12. Can a public member of a package-private class be accessed from another package?

No. The declaring class itself is not accessible outside its package.
