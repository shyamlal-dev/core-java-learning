# Static and Final Keywords

The `static` keyword represents class-level members.  
The `final` keyword restricts modification, overriding, or inheritance.

# Static Keyword

A static member belongs to the class rather than individual objects.

## Static Variable

A static variable has one shared copy for the class.

```java
class Employee {

    private static int employeeCount;
    private final int id;

    Employee(int id) {
        this.id = id;
        employeeCount++;
    }

    static int getEmployeeCount() {
        return employeeCount;
    }
}
```

```java
Employee first = new Employee(101);
Employee second = new Employee(102);

System.out.println(Employee.getEmployeeCount()); // 2
```

Use static variables for data genuinely shared by all objects.

## Static Method

A static method belongs to the class.

```java
class NumberUtility {

    static boolean isEven(int number) {
        return number % 2 == 0;
    }
}
```

Call it using the class name:

```java
NumberUtility.isEven(10);
```

A static method can directly access:

- Static variables
- Static methods

A static method cannot directly access:

- Instance variables
- Instance methods
- `this`
- `super`

It needs an object reference to access instance members.

## Static Block

A static block executes when the class is initialized.

```java
class Configuration {

    static final String ENVIRONMENT;

    static {
        ENVIRONMENT = "production";
    }
}
```

Common uses:

- Complex static-field initialization
- One-time class-level setup
- Validation of static configuration

Avoid heavy I/O and complex business logic in static blocks.

## Static Initialization Order

Static fields and static blocks execute in source-code order when the class is initialized.

```java
class Example {

    static int first = initializeFirst();

    static {
        System.out.println("Static block");
    }

    static int second = initializeSecond();
}
```

Static initialization generally happens once per class loader.

## Static Nested Class

A static nested class does not require an outer-class object.

```java
class Outer {

    static class Nested {
        void display() {
            System.out.println("Static nested class");
        }
    }
}
```

```java
Outer.Nested nested = new Outer.Nested();
```

# Final Keyword

The meaning of `final` depends on where it is used.

## Final Variable

A final variable can be assigned only once.

```java
final int employeeId = 101;
```

A blank final variable can be initialized later exactly once.

```java
class Employee {

    private final int id;

    Employee(int id) {
        this.id = id;
    }
}
```

Every constructor must initialize an uninitialized final instance field.

## Final Reference

A final reference cannot point to another object.

```java
final List<String> skills = new ArrayList<>();
skills.add("Java"); // Allowed
```

The referenced mutable object may still change.

This is invalid:

```java
skills = new ArrayList<>();
```

Therefore, `final` does not automatically make an object immutable.

## Final Method

A final method cannot be overridden.

```java
class Payment {

    final void validateAmount(double amount) {
        if (amount <= 0) {
            throw new IllegalArgumentException("Invalid amount");
        }
    }
}
```

Use final methods when behavior must remain unchanged in child classes.

## Final Class

A final class cannot be extended.

```java
final class SecurityToken {
}
```

Important examples include `String` and wrapper classes.

A final class is not automatically immutable. Its internal mutable state must still be protected.

## Constants

A constant is generally declared using:

```java
private static final int MAX_RETRY_COUNT = 3;
```

- `static`: One class-level value
- `final`: Assigned only once

Use uppercase names with underscores for constants.

## Static Method Hiding

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

Method selection depends on the reference or class type.

Prefer:

```java
Parent.display();
Child.display();
```

## Final vs Immutable

### Final

Restricts reassignment of a variable or reference.

### Immutable

Prevents changes to object state after construction.

An immutable class usually requires:

- Private final fields
- Constructor validation
- No mutating methods
- Defensive copies
- No exposure of mutable internal state

## Common Mistakes

- Accessing instance members directly from static methods
- Calling static methods through object references
- Treating static methods as overridden
- Assuming a final reference makes the object immutable
- Using global mutable static state
- Performing heavy work inside static blocks
- Using final classes without protecting mutable fields

## Summary

- Static members belong to the class.
- Static variables are shared by all objects.
- Static methods cannot directly access instance state.
- Static methods are hidden, not overridden.
- Final variables can be assigned only once.
- Final methods cannot be overridden.
- Final classes cannot be extended.
- Final references do not make mutable objects immutable.
