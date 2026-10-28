# SOLID Principles Assignments

## Coding Questions

### 1. Refactor an Order God Class

An `OrderManager` currently:

- Validates orders
- Calculates discounts
- Saves orders
- Processes payments
- Sends notifications
- Generates invoices

### Requirements

- Separate independent responsibilities.
- Keep the main order workflow readable.
- Make components independently testable.
- Avoid unnecessary inheritance.

---

### 2. Build an Extensible Discount Engine

Support discounts for:

- Regular customers
- Premium customers
- Festival campaigns
- Large orders

### Requirements

- Avoid a long `if-else` chain.
- Create independently testable discount policies.
- Add new policies without modifying existing policy classes.
- Define how multiple discounts are combined.

---

### 3. Identify and Fix an LSP Violation

A base `Account` class supports withdrawal, but a child fixed-deposit account throws an exception for every withdrawal.

### Requirements

- Explain why substitutability is broken.
- Refactor the abstraction.
- Separate withdrawable and non-withdrawable accounts.
- Ensure callers depend on the correct contract.

---

### 4. Apply Interface Segregation

A large device interface contains:

- Print
- Scan
- Fax
- Copy
- Email document

A basic printer is forced to implement every method.

### Requirements

- Split the interface into focused contracts.
- Let each device implement only supported capabilities.
- Avoid empty or unsupported method implementations.

---

### 5. Apply Dependency Inversion

An `OrderService` directly creates:

- MySQL repository
- Email notification service
- Credit-card payment processor

### Requirements

- Introduce suitable abstractions.
- Inject mandatory dependencies through the constructor.
- Allow test implementations.
- Keep high-level business logic independent of infrastructure classes.

---

### 6. Design a Notification System

Support:

- Email
- SMS
- Push notification

### Requirements

- Apply OCP and DIP.
- Keep each channel independently testable.
- Avoid modifying the main notification dispatcher when adding a channel.
- Report delivery success or failure clearly.

---

### 7. Review an Over-Engineered Design

A simple calculator has:

- Eight interfaces
- Six factories
- Four abstract classes
- One implementation for every abstraction

### Requirements

- Identify unnecessary abstractions.
- Simplify the design.
- Retain only abstractions representing actual variation.
- Explain the trade-off between extensibility and simplicity.

---

## Interview Questions and Answers

### 1. What does SOLID represent?

SOLID represents Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, and Dependency Inversion principles.

### 2. What is the Single Responsibility Principle?

A class should have one primary responsibility or one primary reason to change.

### 3. Does SRP mean a class should contain only one method?

No. A class may contain multiple methods related to one cohesive responsibility.

### 4. What is the Open/Closed Principle?

Software should support extension without requiring unnecessary modification of stable existing behavior.

### 5. Does OCP mean existing classes can never be changed?

No. It encourages extension through abstractions when variation is expected, not complete prevention of modification.

### 6. What is the Liskov Substitution Principle?

A subtype must be usable wherever its parent type is expected without breaking the caller's valid assumptions.

### 7. What is the Interface Segregation Principle?

Clients should depend only on the methods they actually require.

### 8. What is the Dependency Inversion Principle?

High-level and low-level modules should depend on abstractions rather than high-level modules directly depending on concrete implementations.

### 9. Are dependency inversion and dependency injection the same?

No. Dependency inversion is a design principle. Dependency injection is a technique used to supply dependencies and can help implement the principle.

### 10. Why is constructor injection generally preferred?

It makes mandatory dependencies explicit, supports immutability, and prevents incomplete object creation.

### 11. What is a common LSP violation?

A child class that rejects operations valid for the parent or changes their expected meaning violates substitutability.

### 12. Can SOLID be overused?

Yes. Unnecessary interfaces and abstraction layers can make simple code more complex and difficult to navigate.

### 13. How does SOLID improve testing?

Focused responsibilities and abstraction-based dependencies allow components to be isolated and replaced with controlled test implementations.
