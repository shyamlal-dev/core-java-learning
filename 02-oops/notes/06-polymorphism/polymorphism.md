# Polymorphism

Polymorphism means one interface or reference type can represent different forms of objects.

```java
Employee employee = new Developer();
employee.work();
```

The reference type is `Employee`, but the actual object type is `Developer`.

## Types of Polymorphism

Java mainly supports:

1. Compile-time polymorphism through method overloading
2. Runtime polymorphism through method overriding

## Static Polymorphism

Static polymorphism is achieved through method overloading.

```java
class Calculator {

    int add(int first, int second) {
        return first + second;
    }

    double add(double first, double second) {
        return first + second;
    }
}
```

The compiler selects the method based on:

- Number of arguments
- Argument types
- Argument order

Return type alone cannot overload a method.

## Dynamic Polymorphism

Dynamic polymorphism is achieved through method overriding.

```java
class Employee {

    void work() {
        System.out.println("Employee is working");
    }
}

class Developer extends Employee {

    @Override
    void work() {
        System.out.println("Developer is writing code");
    }
}
```

```java
Employee employee = new Developer();
employee.work();
```

Output:

```text
Developer is writing code
```

The overridden method is selected using the actual object type at runtime.

## Upcasting

Upcasting means storing a child object in a parent reference.

```java
Employee employee = new Developer();
```

Upcasting:

- Happens implicitly
- Supports runtime polymorphism
- Restricts direct access to child-specific members

```java
employee.work(); // Allowed
// employee.writeCode(); // Not accessible through Employee reference
```

## Downcasting

Downcasting converts a parent reference back to a child reference.

```java
if (employee instanceof Developer) {
    Developer developer = (Developer) employee;
    developer.writeCode();
}
```

Incorrect downcasting causes `ClassCastException`.

Prefer polymorphic methods over frequent downcasting.

## Polymorphism with Variables

Instance variables are not polymorphic. They are hidden, not overridden.

```java
class Parent {
    String value = "Parent";
}

class Child extends Parent {
    String value = "Child";
}
```

```java
Parent reference = new Child();

System.out.println(reference.value);
```

Output:

```text
Parent
```

Field access is decided by the reference type at compile time.

## Polymorphism with Instance Methods

Overridden instance methods support runtime polymorphism.

```java
Parent reference = new Child();
reference.display();
```

The actual object type decides which overridden method executes.

This process is called dynamic method dispatch.

## Polymorphism with Static Methods

Static methods are hidden, not overridden.

```java
class Parent {

    static void display() {
        System.out.println("Parent");
    }
}

class Child extends Parent {

    static void display() {
        System.out.println("Child");
    }
}
```

```java
Parent reference = new Child();
reference.display();
```

Output:

```text
Parent
```

Static method selection depends on the reference type because static methods belong to classes.

Prefer calling static methods using the class name:

```java
Parent.display();
```

## Polymorphism with Private Methods

Private methods are not inherited and cannot be overridden.

```java
class Parent {

    private void display() {
    }
}

class Child extends Parent {

    private void display() {
    }
}
```

These are two unrelated methods.

## Polymorphism with Final Methods

A final method cannot be overridden.

```java
class Parent {

    final void display() {
        System.out.println("Fixed behavior");
    }
}
```

A child class inherits the method but cannot replace its implementation.

## Final Class

A final class cannot be extended.

```java
final class SecurityToken {
}
```

```java
// Invalid
class CustomToken extends SecurityToken {
}
```

A final class may still contain mutable objects unless immutability is designed explicitly.

## Overriding Rules

An overriding method:

- Must have the same method signature
- Must have the same or covariant return type
- Cannot reduce method visibility
- Cannot override static methods
- Cannot override private methods
- Cannot override final methods
- Cannot throw broader checked exceptions

Use `@Override` to detect mistakes at compile time.

## Covariant Return Type

An overriding method may return a subtype of the parent's return type.

```java
class Parent {

    Number getValue() {
        return 10;
    }
}

class Child extends Parent {

    @Override
    Integer getValue() {
        return 20;
    }
}
```

## Overloading Resolution

Overloading is resolved at compile time using the declared argument types.

```java
void display(Object value) {
    System.out.println("Object");
}

void display(String value) {
    System.out.println("String");
}
```

```java
Object value = "Java";
display(value);
```

Output:

```text
Object
```

The compiler uses the declared type `Object`.

## Common Mistakes

- Calling field hiding variable polymorphism
- Treating static method hiding as overriding
- Overloading methods only by return type
- Performing unsafe downcasting
- Forgetting `@Override`
- Using `instanceof` repeatedly instead of polymorphism
- Expecting private methods to be overridden

## Summary

- Overloading provides compile-time polymorphism.
- Overriding provides runtime polymorphism.
- Instance methods are dynamically dispatched.
- Variables are selected using reference type.
- Static methods are hidden, not overridden.
- Private and final methods cannot be overridden.
- Use polymorphism to replace type-checking conditions.
