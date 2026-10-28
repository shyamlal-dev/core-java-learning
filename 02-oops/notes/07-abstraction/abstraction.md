# Abstraction

Abstraction exposes essential behavior while hiding unnecessary implementation details.

A caller should depend on what an object does rather than how it performs the operation.

## Abstract Class

An abstract class is declared using the `abstract` keyword.

```java
abstract class Payment {

    abstract void process(double amount);
}
```

An abstract class:

- Cannot be instantiated directly
- May contain abstract methods
- May contain concrete methods
- May contain fields and constructors
- May contain static and final methods
- Can implement interfaces

## Abstract Method

An abstract method declares behavior without providing its implementation.

```java
abstract void process(double amount);
```

An abstract method:

- Has no method body
- Must be implemented by a concrete child class
- Cannot be `private`
- Cannot be `static`
- Cannot be `final`

These modifiers conflict with overriding.

## Concrete Method in an Abstract Class

```java
abstract class Payment {

    abstract void process(double amount);

    void validateAmount(double amount) {
        if (amount <= 0) {
            throw new IllegalArgumentException("Amount must be positive");
        }
    }
}
```

Abstract classes can provide common reusable behavior.

## Constructor in an Abstract Class

An abstract class can have a constructor.

```java
abstract class Employee {

    private final int id;

    protected Employee(int id) {
        this.id = id;
    }
}
```

The constructor initializes the parent portion of a child object.

## Implementing an Abstract Class

```java
class UpiPayment extends Payment {

    @Override
    void process(double amount) {
        validateAmount(amount);
        System.out.println("Processing UPI payment");
    }
}
```

A concrete child class must implement all inherited abstract methods.

Otherwise, the child class must also be abstract.

## Abstract Class Without Abstract Methods

An abstract class may contain no abstract methods.

```java
abstract class UtilityBase {

    void log() {
        System.out.println("Logging");
    }
}
```

This prevents direct instantiation while allowing controlled inheritance.

## Constructor Call Behavior

```java
Payment payment = new UpiPayment();
```

During object creation:

1. Abstract parent-class constructor executes.
2. Child-class constructor executes.

An abstract-class reference can point to a concrete child object.

## Abstraction Through Interfaces

An interface defines a contract that implementations must follow.

```java
interface NotificationService {
    void send(String message);
}
```

Both abstract classes and interfaces support abstraction, but their use cases differ.

## When to Use an Abstract Class

Use an abstract class when:

- Related classes share state.
- Common implementation is required.
- Constructors are needed.
- Protected helper methods are useful.
- A strong parent-child relationship exists.

## Design Guidelines

- Keep abstractions focused.
- Do not create an abstract class only for code reuse.
- Avoid deep abstract-class hierarchies.
- Do not call overridable methods from constructors.
- Keep parent-class contracts stable.
- Prefer interfaces when unrelated implementations need the same contract.

## Common Mistakes

- Trying to instantiate an abstract class
- Declaring abstract methods as private
- Calling abstract methods from constructors
- Creating abstractions with no real variation
- Using abstract classes where composition is more suitable
- Exposing unnecessary implementation details

## Summary

- Abstraction exposes required behavior and hides implementation.
- Abstract classes cannot be instantiated directly.
- Abstract methods must be implemented by concrete child classes.
- Abstract classes can contain state, constructors, and concrete methods.
- Use abstract classes for related classes sharing state or implementation.
