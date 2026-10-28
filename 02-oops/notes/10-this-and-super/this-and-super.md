# `this` and `super`

`this` and `super` are reference-related keywords used inside instance contexts.

- `this` refers to the current object.
- `super` refers to the immediate parent-class portion of the current object.

## `this` Keyword

## Access Current Object Fields

`this` resolves name conflicts between fields and parameters.

```java
class Employee {

    private int id;
    private String name;

    Employee(int id, String name) {
        this.id = id;
        this.name = name;
    }
}
```

Without `this`, the parameters would assign values to themselves.

## Call Current-Class Method

```java
class Employee {

    void display() {
        this.printDetails();
    }

    void printDetails() {
        System.out.println("Employee details");
    }
}
```

`this` is optional when there is no ambiguity.

## Constructor Chaining Using `this()`

```java
class Employee {

    private int id;
    private String name;

    Employee() {
        this(0, "Unknown");
    }

    Employee(int id, String name) {
        this.id = id;
        this.name = name;
    }
}
```

Rules:

- `this()` calls another constructor in the same class.
- It must be the first constructor statement.
- Recursive constructor chaining is not allowed.

## Pass Current Object

```java
class Employee {

    void register() {
        EmployeeRegistry.add(this);
    }
}
```

Use this carefully. Publishing `this` before construction completes may expose a partially initialized object.

## Return Current Object

```java
class QueryBuilder {

    QueryBuilder select(String field) {
        return this;
    }
}
```

Returning `this` enables fluent APIs.

## `this` Restrictions

`this` cannot be used directly inside a static context because static members belong to the class, not an object.

```java
static void display() {
    // System.out.println(this); // Invalid
}
```

## `super` Keyword

## Call Parent Constructor

```java
class Employee {

    Employee(int id) {
    }
}

class Developer extends Employee {

    Developer(int id) {
        super(id);
    }
}
```

Rules:

- `super()` must be the first constructor statement.
- If not explicitly written, the compiler attempts to insert `super()`.
- The required parent constructor must be accessible.

## Access Parent Method

```java
class Employee {

    void work() {
        System.out.println("General work");
    }
}

class Developer extends Employee {

    @Override
    void work() {
        super.work();
        System.out.println("Writing code");
    }
}
```

## Access Hidden Parent Field

```java
class Parent {
    String value = "Parent";
}

class Child extends Parent {
    String value = "Child";

    void display() {
        System.out.println(this.value);
        System.out.println(super.value);
    }
}
```

Fields are hidden, not overridden.

## `this()` vs `super()`

```text
this()   -> Calls another constructor in the same class
super()  -> Calls a constructor in the immediate parent class
```

Both must be the first constructor statement. Therefore, both cannot be explicitly called from the same constructor.

However, a constructor called using `this()` eventually calls a parent constructor.

## `this` and `super` in Static Context

Neither `this` nor `super` can be used directly inside a static method.

A static method has no current object.

## `this` in Inner Classes

Inside an inner class:

```java
this
```

refers to the inner-class object.

The outer object can be referenced using:

```java
OuterClass.this
```

## Important Clarification

`super` is not a separate parent object.

A child object contains the inherited parent state as part of the same object. `super` provides access to the immediate parent implementation.

## Constructor Execution Example

```java
class Parent {

    Parent() {
        System.out.println("Parent constructor");
    }
}

class Child extends Parent {

    Child() {
        super();
        System.out.println("Child constructor");
    }
}
```

Output:

```text
Parent constructor
Child constructor
```

## Common Mistakes

- Forgetting `this` during field assignment
- Calling `this()` after another statement
- Calling both `this()` and `super()` explicitly
- Creating recursive constructor chains
- Using `this` inside a static method
- Assuming `super` refers to a separate object
- Publishing `this` during construction

## Summary

- `this` refers to the current object.
- `super` provides access to the immediate parent implementation.
- `this()` performs same-class constructor chaining.
- `super()` invokes a parent constructor.
- Both constructor calls must be the first statement.
- Neither keyword can be directly used in static methods.
