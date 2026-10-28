# Class and Object Assignments

## Coding Questions

### 1. Create an Employee Class

Create an `Employee` class containing:

- Employee ID
- Name
- Department
- Salary

### Requirements

- Initialize mandatory fields through a constructor.
- Keep fields private.
- Reject invalid salary values.
- Provide a method to display employee details.
- Create multiple employee objects.

---

### 2. Demonstrate Reference Assignment

Create one object and assign its reference to two variables.

### Requirements

- Modify the object through the first reference.
- Read the value through the second reference.
- Compare both references using `==`.
- Explain the result.

---

### 3. Design a Bank Account

Create a `BankAccount` class supporting:

- Deposit
- Withdrawal
- Balance enquiry

### Requirements

- Do not expose the balance directly.
- Reject invalid amounts.
- Prevent withdrawal exceeding the available balance.
- Initialize the account in a valid state.

---

### 4. Create an Immutable Product

Create an immutable `Product` containing:

- Product ID
- Name
- Price

### Requirements

- Make all fields private and final.
- Initialize fields through a constructor.
- Validate constructor arguments.
- Do not provide setters.

---

### 5. Demonstrate Object Identity and Equality

Create two employee objects with the same employee ID.

### Requirements

- Compare them using `==`.
- Compare them using `equals()`.
- Override `equals()` and `hashCode()`.
- Store both objects in a `HashSet` and observe the result.

---

### 6. Model an Order and Order Items

Create:

- `Order`
- `OrderItem`
- `Product`

### Requirements

- An order may contain multiple items.
- Calculate the order total through behavior.
- Do not allow callers to modify the internal item collection directly.
- Reject invalid item quantities.

---

## Interview Questions and Answers

### 1. What is a class?

A class is a blueprint defining the fields, methods, and constructors of its objects.

### 2. What is an object?

An object is a runtime instance of a class containing state and behavior.

### 3. What is the difference between an object and a reference?

An object contains runtime state. A reference is a value used to access that object.

### 4. Can multiple references point to the same object?

Yes. Changes made through one reference can be observed through another reference pointing to the same object.

### 5. What happens during object creation?

Memory is allocated, fields receive default values, field initializers and initializer blocks execute, and then the constructor runs.

### 6. What is an anonymous object?

It is an object created without storing its reference. It is normally used for a single immediate operation.

### 7. When does an object become eligible for garbage collection?

An object becomes eligible when it is no longer reachable from any live reference.

### 8. What is the difference between identity and equality?

Identity checks whether references point to the same object. Equality checks whether objects are logically equivalent.

### 9. Can an object be created without using `new`?

Yes. Objects may also be created through reflection, cloning, deserialization, factory methods, and JVM-managed mechanisms.

### 10. Why should fields generally be private?

Private fields protect object invariants and prevent uncontrolled external modifications.
