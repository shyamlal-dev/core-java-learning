# Java Naming Conventions

Naming conventions improve readability, maintainability, and consistency. They are conventions rather than compiler rules.

## Packages

Use lowercase names, usually based on a reversed domain.

```java
com.company.project.service
```

Avoid:

```text
Com.Company.Project
```

## Classes and Interfaces

Use PascalCase.

```java
EmployeeService
PaymentProcessor
OrderRepository
```

Names should generally represent nouns or responsibilities.

## Methods

Use camelCase and begin with a verb or action.

```java
calculateSalary()
findEmployeeById()
processPayment()
```

Boolean methods should clearly communicate a condition.

```java
isActive()
hasPermission()
canWithdraw()
```

## Variables

Use camelCase and meaningful names.

```java
employeeCount
totalAmount
customerName
```

Avoid unclear names:

```java
int x;
String str;
Employee e;
```

Short names may be acceptable in a very limited scope, such as loop indexes.

## Constants

Use uppercase letters with underscores.

```java
public static final int MAX_RETRY_COUNT = 3;
private static final String DEFAULT_CURRENCY = "INR";
```

A `final` reference is not automatically a constant if the referenced object is mutable.

## Enums

Enum type names use PascalCase. Enum constants use uppercase letters with underscores.

```java
enum OrderStatus {
    CREATED,
    PAYMENT_PENDING,
    COMPLETED,
    CANCELLED
}
```

## Generic Type Parameters

Common generic parameter names:

- `T`: Type
- `E`: Element
- `K`: Key
- `V`: Value
- `R`: Result
- `N`: Number

```java
interface Repository<T, ID> {
    T findById(ID id);
}
```

Use descriptive names when a generic signature becomes complex.

## Files

A public top-level class name must match its file name exactly.

```text
EmployeeService.java
```

```java
public class EmployeeService {
}
```

## Avoid Misleading Names

A name should describe actual behavior.

Avoid:

```java
List<Employee> employeeSet;
void getEmployee(); // If the method saves an employee
```

Prefer:

```java
Set<Employee> employees;
void saveEmployee();
```

## Naming Guidelines

- Prefer meaningful names over excessive comments.
- Avoid unnecessary abbreviations.
- Use consistent domain terminology.
- Do not encode implementation details into names unnecessarily.
- Avoid single-letter names outside very small scopes.
- Keep names concise but descriptive.

## Summary

- Packages: lowercase
- Classes and interfaces: PascalCase
- Methods and variables: camelCase
- Constants: UPPER_SNAKE_CASE
- Boolean methods: `is`, `has`, or `can`
- Names should reveal purpose and behavior