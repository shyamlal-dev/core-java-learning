# Constructors

A constructor initializes a newly created object.

```java
class Employee {
    private final int id;

    Employee(int id) {
        this.id = id;
    }
}
```

## Constructor Rules

- Constructor name must match the class name.
- A constructor has no return type.
- A constructor runs during object creation.
- Constructors can be overloaded.
- Constructors cannot be inherited.
- Constructors cannot be overridden.
- Constructors may use access modifiers.
- Constructors cannot be `static`, `final`, or `abstract`.

## Default Constructor

If no constructor is declared, the compiler provides a no-argument default constructor.

```java
class Employee {
}
```

Conceptually:

```java
Employee() {
    super();
}
```

If any constructor is explicitly declared, the compiler does not provide the default constructor.

## No-Argument Constructor

A no-argument constructor is explicitly written without parameters.

```java
Employee() {
    name = "Unknown";
}
```

A no-argument constructor and compiler-generated default constructor are not exactly the same.

## Parameterized Constructor

```java
Employee(int id, String name) {
    this.id = id;
    this.name = name;
}
```

Use parameterized constructors for mandatory object state.

## Constructor Overloading

```java
Employee() {
    this(0, "Unknown");
}

Employee(int id, String name) {
    this.id = id;
    this.name = name;
}
```

Constructor overloading provides different valid object-creation options.

## Constructor Chaining

### Using `this()`

Calls another constructor in the same class.

```java
Employee() {
    this(0, "Unknown");
}
```

### Using `super()`

Calls a parent-class constructor.

```java
Developer(int id) {
    super(id);
}
```

Rules:

- `this()` or `super()` must be the first constructor statement.
- Both cannot be called explicitly in the same constructor.
- If neither is written, the compiler inserts `super()`.

## Constructor Execution Order

For inheritance:

1. Parent static initialization
2. Child static initialization
3. Parent instance fields and initializer blocks
4. Parent constructor
5. Child instance fields and initializer blocks
6. Child constructor

Static initialization happens once when the class is initialized.

## Private Constructor

A private constructor prevents direct object creation outside the class.

Common uses:

- Utility classes
- Singleton implementations
- Controlled factory methods

```java
final class Utility {
    private Utility() {
        throw new AssertionError("No instances");
    }
}
```

## Constructor vs Method

A constructor initializes an object. A method performs behavior after construction.

A constructor:

- Has the class name
- Has no return type
- Runs during object creation
- Cannot be overridden

## Constructor Guidelines

- Establish valid object state.
- Validate mandatory input.
- Avoid calling overridable methods.
- Avoid heavy I/O operations.
- Avoid publishing `this` during construction.
- Prefer constructor injection for mandatory dependencies.
- Keep the number of parameters manageable.

## Summary

- Constructors initialize objects.
- The compiler provides a default constructor only when no constructor is declared.
- Constructor chaining uses `this()` and `super()`.
- Parent construction completes before child construction.
- Constructors cannot be inherited or overridden.
