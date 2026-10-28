# OOP Introduction Assignments

## Coding Questions

### 1. Model an Employee

Create an `Employee` class containing:

- Employee ID
- Name
- Department
- Salary
- Work behavior

### Requirements

- Keep object state private.
- Validate salary before assigning it.
- Provide behavior instead of exposing every field directly.
- Create and use multiple employee objects.

---

### 2. Design a Payment Model

Create a payment abstraction with:

- Credit-card payment
- UPI payment
- Bank-transfer payment

### Requirements

- Define a common payment contract.
- Demonstrate runtime polymorphism.
- Avoid type checking using `instanceof`.
- Keep payment-specific behavior inside its implementation.

---

### 3. Model a Car Using Composition

Create:

- `Car`
- `Engine`
- `NavigationSystem`

### Requirements

- Use HAS-A relationships.
- Inject dependencies through the constructor.
- Do not make `Car` extend `Engine`.
- Demonstrate replacing one navigation implementation with another.

---

### 4. Identify OOP Principles

Create a small bank-account model demonstrating:

- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

Explain where each principle is used.

---

### 5. Refactor Procedural Code

A program uses one method containing conditions for calculating salaries of developers, managers, and contractors.

Refactor the program using OOP.

### Requirements

- Avoid a long conditional chain.
- Use a common abstraction.
- Keep salary calculation inside the relevant class.
- Make new employee types easy to add.

---

## Interview Questions and Answers

### 1. What is OOP?

OOP is a programming approach that models software using objects containing state and behavior.

### 2. What are the four main OOP principles?

Encapsulation, inheritance, polymorphism, and abstraction.

### 3. What is the difference between a class and an object?

A class is a blueprint. An object is a runtime instance created from that class.

### 4. What is an IS-A relationship?

An IS-A relationship represents inheritance or interface implementation, such as `Developer IS-A Employee`.

### 5. What is a HAS-A relationship?

A HAS-A relationship represents one object containing or using another object, such as `Car HAS-A Engine`.

### 6. Why is composition often preferred over inheritance?

Composition produces lower coupling, avoids rigid inheritance hierarchies, and allows behavior to be replaced more easily.

### 7. Is Java completely object-oriented?

No. Java supports primitive types such as `int`, `char`, and `boolean`, which are not objects.

### 8. Does using classes automatically make a design object-oriented?

No. Good OOP requires meaningful responsibilities, encapsulated state, suitable relationships, and appropriate abstractions.
