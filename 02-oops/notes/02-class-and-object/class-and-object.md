# Class and Object

## Class

A class defines the state and behavior of its objects.

```java
class Employee {
    private int id;
    private String name;

    void displayDetails() {
        System.out.println(id + " " + name);
    }
}
```

- Fields represent state.
- Methods represent behavior.
- Constructors initialize objects.

## Object Creation

```java
Employee employee = new Employee();
```

The statement includes:

1. `Employee employee`: Declares a reference variable.
2. `new Employee()`: Creates an object.
3. `=`: Assigns the object reference to the variable.

The reference and object are different concepts.

```java
Employee first = new Employee();
Employee second = first;
```

Both references point to the same object.

## Object Creation Process

During normal object creation:

1. JVM allocates memory for the object.
2. Instance variables receive default values.
3. Explicit field initializers execute.
4. Instance initializer blocks execute.
5. The constructor executes.
6. A reference to the object is returned.

Parent-class initialization happens before child-class initialization.

## Instance Variable Initialization

Instance variables can be initialized through:

### Direct Initialization

```java
class Employee {
    private String company = "ABC";
}
```

### Constructor

```java
class Employee {
    private final int id;

    Employee(int id) {
        this.id = id;
    }
}
```

### Method

```java
void updateName(String name) {
    this.name = name;
}
```

Prefer constructors for mandatory state and methods for valid state changes.

## Object State and Behavior

An object should protect its state and provide meaningful operations.

Prefer:

```java
account.deposit(500);
```

Instead of:

```java
account.balance = account.balance + 500;
```

## Anonymous Object

An object can be created without storing its reference.

```java
new Employee().displayDetails();
```

Use anonymous objects only when the object is needed once and no reference is required later.

## Object Eligibility for Garbage Collection

An object becomes eligible for garbage collection when it is no longer reachable through any live reference.

```java
Employee employee = new Employee();
employee = null;
```

Eligibility does not guarantee immediate garbage collection.

## Object Identity and Equality

### Identity

Two references point to the same object.

```java
first == second
```

### Logical Equality

Two objects represent the same logical value.

```java
first.equals(second)
```

Logical equality requires a suitable `equals()` implementation.

## Access Specifiers

Access modifiers control visibility:

- `private`
- package-private
- `protected`
- `public`

Prefer the most restrictive access that supports the required design.

## Class Design Guidelines

- Keep fields private.
- Initialize mandatory fields through constructors.
- Avoid partially initialized objects.
- Give a class one focused responsibility.
- Expose behavior instead of mutable state.
- Validate state changes.
- Prefer immutable objects where practical.

## Summary

- A class defines fields, methods, and constructors.
- An object is an instance of a class.
- Reference variables point to objects.
- Instance fields receive default values.
- Constructors should establish valid object state.
- Identity and logical equality are different.
