# Abstraction Assignments

## Coding Questions

### 1. Design a Payment Abstraction

Create an abstract `Payment` class supporting:

- Payment validation
- Payment processing
- Transaction ID generation

Create implementations for:

- UPI payment
- Card payment
- Bank-transfer payment

### Requirements

- Keep common validation in the abstract class.
- Keep payment-specific processing in child classes.
- Prevent direct creation of the abstract class.
- Process payments through the abstract reference type.

---

### 2. Create an Employee Salary Model

Create an abstract `Employee` class containing:

- Employee ID
- Name
- Abstract salary-calculation method
- Common employee-details method

Create full-time and contract employee implementations.

---

### 3. Build a Document Processor

Create an abstract document processor with steps for:

1. Reading a document
2. Validating the document
3. Processing the document
4. Saving the result

Create PDF and CSV implementations.

### Requirements

- Reuse the common workflow.
- Allow subclasses to implement format-specific steps.
- Avoid duplicated processing flow.

---

### 4. Create an Abstract Shape Model

Create an abstract `Shape` class.

### Requirements

- Define abstract methods for area and perimeter.
- Validate common dimensions where appropriate.
- Create circle, rectangle, and triangle implementations.
- Process different shapes polymorphically.

---

### 5. Demonstrate an Abstract-Class Constructor

Create an abstract parent class with:

- Final ID field
- Constructor
- Abstract method
- Concrete method

Create a child class and print constructor execution order.

---

### 6. Prevent Invalid Instantiation

Create an abstract base class without any abstract method.

### Requirements

- Explain why direct instantiation is prevented.
- Create valid child implementations.
- Demonstrate shared behavior.

---

### 7. Refactor Duplicate Processing Logic

Two report classes duplicate validation, logging, execution, and error-handling logic.

Refactor the common workflow into an abstract class while keeping report-specific generation in child classes.

---

## Interview Questions and Answers

### 1. What is abstraction?

Abstraction exposes essential behavior while hiding unnecessary implementation details.

### 2. What is an abstract class?

An abstract class is a class that cannot be instantiated directly and may contain abstract and concrete methods.

### 3. What is an abstract method?

An abstract method declares a method signature without an implementation and must be implemented by a concrete child class.

### 4. Can an abstract class have a constructor?

Yes. The constructor initializes the abstract parent portion of child objects.

### 5. Can an abstract class contain concrete methods?

Yes. It can contain abstract methods, concrete methods, fields, constructors, and static methods.

### 6. Can an abstract class exist without an abstract method?

Yes. Declaring the class abstract can be used to prevent direct instantiation.

### 7. Can an abstract method be private?

No. A private method is not visible to subclasses and therefore cannot be overridden.

### 8. Can an abstract method be static?

No. Static methods belong to classes and do not support runtime overriding.

### 9. Can an abstract method be final?

No. An abstract method requires implementation through overriding, while final prevents overriding.

### 10. Can an abstract-class reference hold a child object?

Yes. This is commonly used for runtime polymorphism.

### 11. When should an abstract class be preferred over an interface?

Use an abstract class when related classes need shared state, constructors, protected members, or common implementation.

### 12. What happens when a child does not implement all abstract methods?

The child class must also be declared abstract.
