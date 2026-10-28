# Association, Aggregation, and Composition

These relationships describe how objects are connected and collaborate.

# Association

Association is a general relationship where one object knows about or uses another object.

```java
class Doctor {

    void examine(Patient patient) {
        System.out.println("Examining patient");
    }
}
```

A doctor and patient can exist independently.

Association may be:

- One-to-one
- One-to-many
- Many-to-one
- Many-to-many

## One-to-One Association

```text
Person <-> Passport
```

One person is associated with one passport.

## One-to-Many Association

```text
Department -> Employees
```

One department may be associated with multiple employees.

## Many-to-Many Association

```text
Students <-> Courses
```

A student may join multiple courses, and a course may contain multiple students.

# Aggregation

Aggregation is a weak HAS-A relationship.

The contained object can exist independently of the container.

```java
class Department {

    private final List<Employee> employees;

    Department(List<Employee> employees) {
        this.employees = List.copyOf(employees);
    }
}
```

Employees may continue to exist even if the department is removed.

Examples:

- Department has employees
- Team has players
- Library has books

Aggregation expresses ownership or grouping without strict lifecycle dependency.

# Composition

Composition is a strong HAS-A relationship.

The contained object is strongly owned by the container and its lifecycle is controlled by the container.

```java
class House {

    private final List<Room> rooms;

    House(int roomCount) {
        this.rooms = new ArrayList<>();

        for (int index = 0; index < roomCount; index++) {
            rooms.add(new Room());
        }
    }
}
```

The house creates and owns its rooms.

Examples:

- House has rooms
- Order has order items
- Document has pages

## Aggregation vs Composition

The key difference is lifecycle ownership.

### Aggregation

- Weak ownership
- Child may exist independently
- Objects may be shared
- Container does not fully control the child lifecycle

### Composition

- Strong ownership
- Child belongs to one owner
- Owner controls child creation and lifecycle
- Child is not meaningfully independent in the model

Java has no special syntax for aggregation or composition. The distinction comes from design and ownership.

## Composition Over Inheritance

Inheritance represents:

```text
IS-A
```

Composition represents:

```text
HAS-A
```

Avoid inheritance used only for method reuse.

Incorrect:

```java
class Car extends Engine {
}
```

A car is not an engine.

Prefer:

```java
class Car {

    private final Engine engine;

    Car(Engine engine) {
        this.engine = engine;
    }
}
```

## Benefits of Composition

- Lower coupling
- Replaceable behavior
- Easier testing
- Flexible runtime configuration
- Avoidance of deep inheritance hierarchies
- Better separation of responsibilities

## Dependency Injection and Composition

Constructor injection is commonly used to build object composition.

```java
class OrderService {

    private final PaymentProcessor paymentProcessor;

    OrderService(PaymentProcessor paymentProcessor) {
        this.paymentProcessor = paymentProcessor;
    }
}
```

The service HAS-A payment processor and depends on its contract.

## Defensive Design

When managing associated collections:

- Do not expose mutable internal collections.
- Validate added or removed objects.
- Define ownership clearly.
- Define whether sharing is allowed.
- Keep both sides of bidirectional relationships consistent.

## Bidirectional Relationship

In a bidirectional relationship, both objects reference each other.

```text
Department -> Employees
Employee -> Department
```

This may introduce:

- Synchronization problems
- Infinite recursion in `toString()`
- Serialization cycles
- Complex updates

Use bidirectional relationships only when both directions are needed.

## Common Mistakes

- Calling every HAS-A relationship composition
- Using inheritance only to reuse code
- Exposing mutable child collections
- Creating unnecessary bidirectional references
- Failing to define lifecycle ownership
- Allowing external code to break relationship consistency

## Summary

- Association is a general object relationship.
- Aggregation represents weak ownership.
- Composition represents strong ownership.
- Lifecycle ownership distinguishes aggregation from composition.
- Composition provides flexible behavior reuse.
- Prefer composition when inheritance does not represent a genuine IS-A relationship.
