# SOLID Principles

SOLID is a set of object-oriented design principles that helps create maintainable, testable, and extensible software.

```text
S - Single Responsibility Principle
O - Open/Closed Principle
L - Liskov Substitution Principle
I - Interface Segregation Principle
D - Dependency Inversion Principle
```

SOLID principles are guidelines, not rules that must be applied mechanically.

# Single Responsibility Principle

A class should have one primary reason to change.

Avoid:

```java
class OrderService {

    void createOrder() {
    }

    void saveOrder() {
    }

    void sendEmail() {
    }

    void generateInvoice() {
    }
}
```

Different responsibilities should be separated:

```java
class OrderService {
}

class OrderRepository {
}

class NotificationService {
}

class InvoiceGenerator {
}
```

SRP is about reasons for change, not class size alone.

# Open/Closed Principle

Software components should be open for extension but closed for unnecessary modification.

Avoid:

```java
class DiscountCalculator {

    double calculate(String customerType, double amount) {
        if ("REGULAR".equals(customerType)) {
            return amount * 0.05;
        }

        if ("PREMIUM".equals(customerType)) {
            return amount * 0.10;
        }

        return 0;
    }
}
```

Prefer replaceable strategies:

```java
interface DiscountPolicy {
    double calculate(double amount);
}
```

New policies can be added without modifying existing policy implementations.

OCP does not mean code must never change. It means stable behavior should be extendable through suitable abstractions.

# Liskov Substitution Principle

A child type should be usable wherever its parent type is expected without breaking correct behavior.

If `Developer` extends `Employee`, calling code expecting an `Employee` should work correctly with a `Developer`.

A common violation occurs when a child:

- Rejects valid parent operations
- Changes expected behavior
- Strengthens input requirements
- Weakens output guarantees
- Throws unexpected exceptions

Inheritance should model behavioral substitutability, not only code reuse.

# Interface Segregation Principle

Clients should not depend on methods they do not use.

Avoid:

```java
interface Worker {
    void work();
    void manageTeam();
    void writeCode();
    void approveBudget();
}
```

Prefer focused interfaces:

```java
interface Workable {
    void work();
}

interface CodeWriter {
    void writeCode();
}

interface TeamManager {
    void manageTeam();
}
```

Small interfaces reduce forced implementations and unnecessary coupling.

# Dependency Inversion Principle

High-level modules should depend on abstractions, not concrete low-level implementations.

Avoid:

```java
class OrderService {

    private final EmailNotificationService notificationService =
            new EmailNotificationService();
}
```

Prefer:

```java
class OrderService {

    private final NotificationService notificationService;

    OrderService(NotificationService notificationService) {
        this.notificationService = notificationService;
    }
}
```

Benefits:

- Loose coupling
- Easier testing
- Replaceable implementations
- Clearer dependencies

Dependency Injection is a common technique for applying DIP.

## Dependency Injection Types

### Constructor Injection

Preferred for mandatory dependencies.

```java
OrderService(NotificationService notificationService) {
    this.notificationService = notificationService;
}
```

### Method Injection

Useful when a dependency is needed for one operation.

### Setter Injection

Useful for optional replaceable dependencies, but may allow partially initialized objects.

## SOLID Trade-Offs

Overusing SOLID may produce:

- Too many interfaces
- Unnecessary abstraction layers
- Fragmented code
- Difficult navigation
- Abstractions with only one unlikely-to-change implementation

Introduce abstractions around real variation and boundaries.

## Common Misunderstandings

- SRP does not mean one method per class.
- OCP does not mean code is never modified.
- LSP is about behavior, not only matching method signatures.
- ISP does not require an interface for every class.
- DIP and dependency injection are related but not identical.
- SOLID does not replace simple design and good judgement.

## Summary

- SRP separates independent reasons for change.
- OCP supports extension through stable abstractions.
- LSP requires behavioral substitutability.
- ISP prefers focused client-specific contracts.
- DIP makes high-level logic depend on abstractions.
- Apply SOLID where it improves maintainability and flexibility.
