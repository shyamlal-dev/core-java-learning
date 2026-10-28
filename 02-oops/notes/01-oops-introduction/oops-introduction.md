# Object-Oriented Programming

Object-Oriented Programming organizes software around objects containing state and behavior.

```java
class Employee {
    private int id;
    private String name;

    void work() {
        System.out.println(name + " is working");
    }
}
```

## Class and Object

A class is a blueprint defining fields and methods.

An object is a runtime instance of a class.

```java
Employee employee = new Employee();
```

- `Employee`: Class
- `employee`: Reference variable
- `new Employee()`: Object creation

## Four OOP Principles

### Encapsulation

Encapsulation protects object state and controls access through methods.

```java
class BankAccount {
    private double balance;

    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }
}
```

### Inheritance

Inheritance allows a child class to reuse and extend parent-class behavior.

```java
class Employee {
    void work() {
    }
}

class Developer extends Employee {
}
```

Inheritance represents an **IS-A** relationship.

### Polymorphism

Polymorphism allows the same reference type to represent different object types.

```java
Employee employee = new Developer();
employee.work();
```

The overridden method is selected using the actual object type at runtime.

### Abstraction

Abstraction exposes required behavior while hiding implementation details.

```java
abstract class Payment {
    abstract void process();
}
```

## Relationships

### IS-A

Represented using inheritance or interface implementation.

```text
Developer IS-A Employee
```

### HAS-A

Represented using composition or aggregation.

```text
Car HAS-A Engine
```

Prefer composition when inheritance does not represent a genuine IS-A relationship.

## Benefits of OOP

- Modular code
- Controlled object state
- Reusable abstractions
- Easier maintenance
- Extensible design
- Better testability

## Common Problems

OOP can become harmful when it introduces:

- Deep inheritance hierarchies
- God classes
- Tight coupling
- Unnecessary abstractions
- Classes containing only getters and setters
- Inheritance used only for code reuse

## Summary

- Classes define state and behavior.
- Objects are runtime instances of classes.
- Encapsulation protects state.
- Inheritance represents IS-A relationships.
- Polymorphism supports interchangeable implementations.
- Abstraction hides unnecessary implementation details.
- Composition is generally preferred over inappropriate inheritance.
