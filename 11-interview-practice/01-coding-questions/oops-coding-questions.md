# OOP Coding Questions

These questions test object-oriented modelling, SOLID principles, object relationships, maintainability, and extensible design.

## 1. Design a Bank Account System

Design a banking system supporting:

- Savings accounts
- Current accounts
- Deposits
- Withdrawals
- Balance enquiry
- Transaction history

### Requirements

- Keep account balance encapsulated.
- Prevent invalid deposits and withdrawals.
- Define different withdrawal rules for different account types.
- Use inheritance only for valid IS-A relationships.
- Create appropriate custom exceptions.
- Prevent external modification of transaction history.

---

## 2. Design an Employee Payroll System

Create a payroll system for:

- Full-time employees
- Part-time employees
- Contract employees

### Requirements

- Define a common employee abstraction.
- Implement different salary calculation rules.
- Demonstrate runtime polymorphism.
- Avoid using `instanceof` for salary calculation.
- Allow new employee types without modifying existing implementations.

---

## 3. Design a Notification Service

Create a service that sends notifications through:

- Email
- SMS
- Push notification

### Requirements

- Define a common notification contract.
- Use constructor-based dependency injection.
- Client code must not depend on concrete implementations.
- Adding a new notification channel must not modify existing channels.
- Handle notification failures appropriately.

---

## 4. Design a Payment Processing System

Support payments through:

- Credit card
- UPI
- Bank transfer

### Requirements

- Define a payment abstraction.
- Keep payment validation separate from payment processing.
- Return a structured payment result.
- Handle failed payments appropriately.
- Avoid long `if-else` or `switch` blocks.
- Make new payment methods easy to add.

---

## 5. Create an Immutable Employee Class

Create an immutable employee class containing:

- Employee ID
- Name
- Joining date
- Address
- List of skills

### Requirements

- Make the class completely immutable.
- Use defensive copying for mutable fields.
- Do not expose internal collections.
- Validate required fields during object creation.
- Implement `equals()`, `hashCode()`, and `toString()` correctly.

---

## 6. Design a Library Management System

Model the following:

- Books
- Physical book copies
- Members
- Librarians
- Borrowing and returning
- Due dates and fines

### Requirements

- Distinguish a book from its physical copies.
- Prevent borrowing an unavailable copy.
- Maintain borrowing history.
- Keep fine calculation replaceable.
- Use composition where appropriate.
- Avoid creating one class with every responsibility.

---

## 7. Design a Parking Lot

Support:

- Multiple parking floors
- Different parking spot types
- Cars, motorcycles, and trucks
- Entry tickets
- Parking fee calculation

### Requirements

- Allocate a compatible parking spot.
- Prevent assigning one spot to multiple vehicles.
- Keep fee calculation replaceable.
- Avoid hard-coded vehicle-type checks throughout the application.
- Make the design extensible for new vehicle and spot types.

---

## 8. Implement Object Equality Correctly

Create an `Employee` class containing:

- Employee ID
- Name
- Department

### Requirements

- Define equality based on employee ID.
- Override `equals()` and `hashCode()`.
- Test employee objects with `HashSet` and `HashMap`.
- Demonstrate the issue caused by overriding only `equals()`.
- Explain the risk of modifying fields used in equality after insertion.

---

## 9. Design a Shape Calculation System

Support:

- Circle
- Rectangle
- Triangle

### Requirements

- Calculate area and perimeter.
- Use abstraction and runtime polymorphism.
- Validate dimensions during object creation.
- Avoid placing unrelated fields in a common parent class.
- Allow new shapes without changing existing calculation code.

---

## 10. Refactor a God Class

An `OrderManager` class currently performs:

- Order creation
- Order validation
- Discount calculation
- Payment processing
- Database operations
- Notification sending

Refactor the class into focused components.

### Requirements

- Apply the Single Responsibility Principle.
- Apply dependency inversion.
- Keep the main business workflow readable.
- Make individual components independently testable.
- Avoid unnecessary inheritance.

---

## 11. Design a Configurable Discount Engine

Support discounts based on:

- Customer category
- Order amount
- Promotional campaign
- Payment method

### Requirements

- Avoid a long conditional chain.
- Make every discount rule independently testable.
- Support adding new rules without modifying existing rules.
- Define how multiple applicable discounts are combined.
- Prevent discount calculation from modifying the order.

---

## 12. Design an Order Management System

Support:

- Order creation
- Multiple order items
- Inventory validation
- Discount calculation
- Payment processing
- Order status transitions
- Customer notifications

### Requirements

- Prevent invalid order status transitions.
- Separate order, inventory, payment, and notification responsibilities.
- Support multiple payment and notification implementations.
- Use enums for fixed status values.
- Keep business rules independently testable.

---

## 13. Demonstrate Composition Over Inheritance

Design a vehicle system where vehicles may have different:

- Engines
- Braking systems
- Navigation systems

### Requirements

- Use composition instead of creating a deep inheritance hierarchy.
- Allow individual behavior to be replaced.
- Keep components independently testable.
- Demonstrate constructor-based dependency injection.

---

## 14. Model Object Relationships

Create a university model containing:

- University
- Department
- Professor
- Student
- Address

### Requirements

Demonstrate meaningful examples of:

- Association
- Aggregation
- Composition
- One-to-one relationship
- One-to-many relationship

Explain the lifecycle relationship between the objects.

---

## 15. Design a Document Export System

Support exporting reports into:

- PDF
- CSV
- JSON

### Requirements

- Define a common export contract.
- Keep report generation separate from format conversion.
- Allow new export formats without modifying existing exporters.
- Handle unsupported or failed exports properly.
- Avoid a single class containing all export logic.

---

## 16. Design a Product Inventory Model

Support:

- Products
- Product categories
- Stock addition
- Stock reservation
- Stock release
- Low-stock notifications

### Requirements

- Prevent stock from becoming negative.
- Keep inventory rules inside appropriate domain objects.
- Separate notification logic from inventory logic.
- Use meaningful object relationships.
- Create custom exceptions for invalid inventory operations.

---

## 17. Implement a Builder for a Complex Object

Create an immutable `UserProfile` having optional and required fields.

### Requirements

- Use the Builder pattern.
- Validate required fields before object creation.
- Prevent partially initialized objects.
- Keep the final object immutable.
- Provide readable object construction.

---

## 18. Design a Pluggable Tax Calculation System

Calculate taxes based on:

- Product category
- Customer location
- Tax rules
- Transaction date

### Requirements

- Avoid hard-coded tax conditions in the order class.
- Make tax rules independently testable.
- Allow new tax rules to be introduced.
- Return a structured tax calculation result.
- Keep tax calculation separate from payment processing.