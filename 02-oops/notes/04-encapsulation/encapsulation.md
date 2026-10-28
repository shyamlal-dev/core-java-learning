# Encapsulation

Encapsulation combines state and behavior inside a class and controls access to that state.

It is not limited to creating getters and setters.

## Basic Example

```java
class BankAccount {
    private double balance;

    void deposit(double amount) {
        if (amount <= 0) {
            throw new IllegalArgumentException("Amount must be positive");
        }

        balance += amount;
    }

    double getBalance() {
        return balance;
    }
}
```

The class controls how its balance changes.

## Data Hiding vs Encapsulation

### Data Hiding

Restricts direct access to internal data using access modifiers.

### Encapsulation

Combines data hiding with controlled behavior and valid state management.

A class with private fields and unrestricted setters may still have weak encapsulation.

## Object Invariants

An invariant is a condition that must remain true throughout an object's valid lifetime.

Examples:

- Account balance cannot violate an overdraft policy.
- Order quantity must be positive.
- Employee ID cannot be null.
- Completed orders cannot return to a draft state.

Methods should preserve these invariants.

## Getters and Setters

Do not create getters and setters automatically for every field.

Avoid:

```java
account.setBalance(-1000);
```

Prefer meaningful behavior:

```java
account.withdraw(1000);
```

A meaningful method communicates intent and validates the state change.

## Encapsulating Collections

Returning an internal mutable collection breaks encapsulation.

Avoid:

```java
List<String> getSkills() {
    return skills;
}
```

Safer options include:

```java
List<String> getSkills() {
    return List.copyOf(skills);
}
```

Or provide focused operations:

```java
void addSkill(String skill) {
    skills.add(skill);
}
```

## Encapsulation and Immutability

An immutable object does not change after creation.

Common requirements:

- Private final fields
- Constructor-based initialization
- No mutating methods
- Defensive copies of mutable values
- No exposure of mutable internal state

Encapsulation allows controlled mutation. Immutability prevents mutation after construction.

## Package Encapsulation

Packages can hide implementation classes using package-private access.

Expose only necessary public APIs and keep implementation details inaccessible outside the package.

## Benefits

- Protects valid object state
- Reduces coupling
- Supports internal implementation changes
- Improves testability
- Prevents uncontrolled modification
- Makes business rules explicit

## Common Mistakes

- Providing setters for every field
- Returning mutable collections
- Exposing mutable objects directly
- Keeping validation outside the domain object
- Using public fields
- Creating an anemic object containing only data

## Summary

- Encapsulation protects state through controlled behavior.
- Private fields alone do not guarantee good encapsulation.
- Objects should enforce their own invariants.
- Expose meaningful operations instead of unrestricted setters.
- Protect internal mutable collections and objects.
