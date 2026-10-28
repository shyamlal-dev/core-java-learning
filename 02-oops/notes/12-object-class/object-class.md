# Object Class

`java.lang.Object` is the root class of the Java class hierarchy.

Every class directly or indirectly extends `Object`.

```java
class Employee {
}
```

Conceptually:

```java
class Employee extends Object {
}
```

## Important Object Methods

Common methods inherited from `Object` include:

- `equals()`
- `hashCode()`
- `toString()`
- `getClass()`
- `clone()`
- `wait()`
- `notify()`
- `notifyAll()`
- `finalize()` as a deprecated legacy method

## `toString()`

The default implementation returns a value based on the class name and hash code.

```java
Employee employee = new Employee();
System.out.println(employee);
```

`println()` automatically calls `toString()`.

Override it to provide meaningful object information:

```java
@Override
public String toString() {
    return "Employee{id=" + id + ", name='" + name + "'}";
}
```

Do not include passwords, tokens, or sensitive information.

## `equals()`

The default `equals()` implementation compares object identity similarly to `==`.

Override it when objects need logical equality.

```java
@Override
public boolean equals(Object object) {
    if (this == object) {
        return true;
    }

    if (!(object instanceof Employee)) {
        return false;
    }

    Employee employee = (Employee) object;
    return id == employee.id;
}
```

## Equals Contract

A correct `equals()` implementation should be:

### Reflexive

```text
x.equals(x) must be true
```

### Symmetric

```text
x.equals(y) and y.equals(x) must return the same result
```

### Transitive

```text
If x equals y and y equals z, then x must equal z
```

### Consistent

Repeated calls should return the same result while relevant state remains unchanged.

### Non-null

```text
x.equals(null) must be false
```

## `hashCode()`

`hashCode()` returns an integer hash value.

```java
@Override
public int hashCode() {
    return Integer.hashCode(id);
}
```

## Hash Code Contract

- Equal objects must have equal hash codes.
- Unequal objects may have equal hash codes.
- Hash code should remain consistent while equality fields remain unchanged.

If `equals()` is overridden, `hashCode()` must also be overridden.

## Equality in Hash-Based Collections

`HashMap` and `HashSet` use both:

- `hashCode()` to locate a bucket
- `equals()` to identify the matching key or element

Incorrect implementations may cause:

- Logical duplicates in `HashSet`
- Failed map-key lookups
- Incorrect removal behavior
- Unreachable entries after key mutation

Avoid changing fields used by `equals()` and `hashCode()` while an object is used as a hash key.

## `getClass()`

```java
Class<?> type = employee.getClass();
```

`getClass()` returns the runtime class of the object.

The method is final and cannot be overridden.

## `clone()`

`Object.clone()` creates a field-by-field shallow copy.

Important points:

- The class usually implements `Cloneable`.
- `Cloneable` is a marker interface.
- Mutable referenced objects are shared in a shallow copy.
- `CloneNotSupportedException` may be thrown.

Copy constructors or factory methods are often clearer and safer than `clone()`.

## `wait()`, `notify()`, and `notifyAll()`

These methods support thread coordination using an object's monitor.

They must be called while holding the object's intrinsic lock.

```java
synchronized (lock) {
    lock.wait();
}
```

Calling them without owning the monitor causes `IllegalMonitorStateException`.

Detailed usage belongs to multithreading.

## `finalize()`

`finalize()` was historically called before garbage collection under uncertain conditions.

It is deprecated and should not be used for resource cleanup.

Use:

- Try-with-resources
- `AutoCloseable`
- Explicit lifecycle management

## `==` vs `equals()`

### `==`

Checks reference identity for objects.

### `equals()`

Checks logical equality when properly overridden.

```java
Employee first = new Employee(101);
Employee second = new Employee(101);

System.out.println(first == second);      // false
System.out.println(first.equals(second)); // true, if overridden
```

## Equality and Inheritance

Equality becomes difficult when parent and child classes add different equality fields.

Possible problems include:

- Broken symmetry
- Broken transitivity
- Inconsistent behavior across subclasses

Prefer composition or carefully designed immutable value objects when equality must remain predictable.

## Summary

- Object is the root class of Java classes.
- `toString()` provides a textual representation.
- `equals()` defines logical equality.
- `hashCode()` supports hash-based collections.
- Equal objects must have equal hash codes.
- Avoid mutating hash-key fields.
- `clone()` usually performs a shallow copy.
- `finalize()` should not be used.
