# Inheritance

Inheritance allows a child class to acquire accessible fields and methods from a parent class.

```java
class Employee {
    void work() {
        System.out.println("Employee is working");
    }
}

class Developer extends Employee {
}
```

`Developer` has an IS-A relationship with `Employee`.

## Syntax

```java
class Child extends Parent {
}
```

Java supports single class inheritance. A class can directly extend only one class.

## Inherited Members

A child class can access inherited members according to their access level.

- `public`: Accessible everywhere
- `protected`: Accessible in the package and qualifying subclasses
- package-private: Accessible only in the same package
- `private`: Not directly accessible in the child class

Private members still belong to the parent portion of the object but cannot be directly accessed by the child.

## `super` Keyword

`super` represents the immediate parent-class portion of the current object.

### Access Parent Method

```java
super.work();
```

### Access Hidden Parent Field

```java
super.name;
```

### Call Parent Constructor

```java
Developer(int id) {
    super(id);
}
```

`super()` must be the first constructor statement.

## Protected Access

A `protected` member is accessible:

- Within the same package
- In subclasses from another package through inheritance

A subclass in another package cannot use an arbitrary parent object to access a protected member.

Prefer protected methods over protected mutable fields.

## Types of Inheritance

### Single Inheritance

```text
A -> B
```

One child extends one parent.

### Multilevel Inheritance

```text
A -> B -> C
```

A class extends another derived class.

### Hierarchical Inheritance

```text
    A
   / \
  B   C
```

Multiple classes extend one parent.

### Multiple Inheritance

Java does not support extending multiple classes.

```java
class C extends A, B { // Invalid
}
```

Multiple inheritance of type is supported through interfaces.

### Hybrid Inheritance

A combination of inheritance forms can be achieved using classes and interfaces.

## Constructor Execution

Constructors are not inherited.

When a child object is created:

1. Parent constructor executes.
2. Child constructor executes.

The complete parent portion must be initialized before the child portion.

## Method Overriding

A child class can provide a new implementation of an inherited instance method.

```java
class Employee {
    void work() {
        System.out.println("General work");
    }
}

class Developer extends Employee {
    @Override
    void work() {
        System.out.println("Writing code");
    }
}
```

Use `@Override` to let the compiler verify the override.

## Inheritance and Fields

Fields are hidden, not overridden.

```java
class Parent {
    String value = "Parent";
}

class Child extends Parent {
    String value = "Child";
}
```

Field access depends on the reference type, not the runtime object type.

## `Object` Class

Every class directly or indirectly extends `Object`.

Important inherited methods include:

- `equals()`
- `hashCode()`
- `toString()`
- `getClass()`
- `wait()`
- `notify()`
- `notifyAll()`

## Inheritance vs Composition

Use inheritance when:

- A genuine IS-A relationship exists.
- The child obeys the parent's contract.
- Runtime substitution is meaningful.

Use composition when:

- One object uses another object.
- Behavior must be replaceable.
- Only code reuse is required.
- Inheritance would create tight coupling.

## Fragile Base-Class Problem

Changes in a parent class may unexpectedly affect child classes.

Reduce risk by:

- Keeping inheritance hierarchies shallow
- Designing stable parent contracts
- Avoiding calls to overridable methods from constructors
- Preferring composition where appropriate

## Summary

- Inheritance represents an IS-A relationship.
- Java supports one direct parent class.
- Constructors are not inherited.
- Parent construction occurs before child construction.
- Fields are hidden, while instance methods may be overridden.
- Use inheritance for substitutable types, not only code reuse.
