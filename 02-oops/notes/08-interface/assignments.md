# Interface Assignments

## Coding Questions

### 1. Design a Notification Contract

Create a `NotificationService` interface with implementations for:

- Email
- SMS
- Push notification

### Requirements

- Send notifications through the interface type.
- Avoid concrete-type conditions.
- Use constructor injection in the calling service.
- Make new notification channels easy to add.

---

### 2. Demonstrate Multiple Inheritance

Create interfaces for:

- Printing
- Scanning
- Faxing

Create a multifunction device implementing all three interfaces.

### Requirements

- Keep interface methods focused.
- Demonstrate multiple inheritance of type.
- Avoid one large interface forcing unnecessary methods.

---

### 3. Implement a Callback

Create a file-processing service accepting callbacks for:

- Successful processing
- Failed processing

### Requirements

- Define suitable callback interfaces.
- Pass callback implementations from the caller.
- Invoke the correct callback based on the result.
- Implement callbacks using both classes and lambdas.

---

### 4. Resolve a Default-Method Conflict

Create two interfaces containing the same default method.

### Requirements

- Implement both interfaces in one class.
- Resolve the conflict explicitly.
- Call a selected interface implementation using `InterfaceName.super`.
- Explain the conflict-resolution rule.

---

### 5. Create a Functional Interface

Create a functional interface for applying a discount.

### Requirements

- Accept original amount and discount rate.
- Return the discounted amount.
- Implement it using a lambda.
- Add one default method and one static method.
- Use `@FunctionalInterface`.

---

### 6. Apply Interface Segregation

A large `Worker` interface requires:

- Work
- Eat
- Sleep
- Manage team
- Write code

Refactor it into focused interfaces so implementations depend only on required methods.

---

### 7. Compare Interface and Abstract Class

Create a payment model where:

- All payment types share a processing contract.
- Some related payment classes share validation state and behavior.

Use an interface and an abstract class together where appropriate.

---

### 8. Create a Strategy-Based Tax Calculator

Create a `TaxCalculator` interface with multiple tax strategies.

### Requirements

- Inject the strategy into an order service.
- Do not hard-code tax conditions in the service.
- Allow the strategy to be changed.
- Keep each implementation independently testable.

---

## Interview Questions and Answers

### 1. What is an interface?

An interface defines a contract that implementing classes must follow.

### 2. Can a class implement multiple interfaces?

Yes. This provides multiple inheritance of type.

### 3. Can an interface extend another interface?

Yes. An interface can extend one or multiple interfaces.

### 4. What are the implicit modifiers of interface fields?

Interface fields are implicitly `public static final`.

### 5. What are the implicit modifiers of traditional interface methods?

They are implicitly `public abstract`.

### 6. What is a default method?

A default method is an interface method with an implementation. It was introduced in Java 8 primarily to support interface evolution.

### 7. Can an implementing class reduce the visibility of an interface method?

No. The implementation must be public.

### 8. Are static interface methods inherited?

No. They belong to the interface and are called using the interface name.

### 9. What happens when two interfaces contain the same default method?

The implementing class must override the method and explicitly resolve the conflict.

### 10. What is a callback?

A callback is behavior supplied by a caller and executed by another component after or during an operation.

### 11. What is a functional interface?

A functional interface has exactly one abstract method and can be implemented using a lambda expression.

### 12. Can a functional interface contain default and static methods?

Yes. Only the number of abstract methods is restricted.

### 13. What is the difference between an interface and an abstract class?

Interfaces primarily define capabilities and support multiple implementation contracts. Abstract classes can contain instance state, constructors, and shared implementation.

### 14. Can an interface have a constructor?

No. Interfaces cannot be instantiated and do not have instance-construction state.

### 15. What is a marker interface?

A marker interface contains no methods and indicates metadata or capability through the type system.
