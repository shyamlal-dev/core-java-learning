# Interface

An interface defines a contract that implementing classes must follow.

```java
interface PaymentProcessor {
    void process(double amount);
}
```

```java
class UpiPaymentProcessor implements PaymentProcessor {

    @Override
    public void process(double amount) {
        System.out.println("Processing UPI payment");
    }
}
```

## Interface Methods

In Java 8, an interface may contain:

- Abstract methods
- Default methods
- Static methods

```java
interface PaymentProcessor {

    void process(double amount);

    default void printReceipt() {
        System.out.println("Receipt generated");
    }

    static boolean isValidAmount(double amount) {
        return amount > 0;
    }
}
```

Private interface methods were introduced after Java 8 and can support internal reuse in modern Java.

## Interface Fields

Fields declared in an interface are implicitly:

```text
public static final
```

```java
interface Configuration {
    int MAX_RETRY_COUNT = 3;
}
```

Interface fields are constants and must be initialized.

Do not use interfaces only as constant containers.

## Interface Method Visibility

Traditional abstract interface methods are implicitly:

```text
public abstract
```

An implementing method must be `public`.

```java
interface Service {
    void execute();
}

class ServiceImpl implements Service {

    @Override
    public void execute() {
    }
}
```

Reducing visibility causes a compilation error.

## Multiple Inheritance Using Interfaces

A class can implement multiple interfaces.

```java
interface Printable {
    void print();
}

interface Scannable {
    void scan();
}

class MultiFunctionPrinter implements Printable, Scannable {

    @Override
    public void print() {
    }

    @Override
    public void scan() {
    }
}
```

This provides multiple inheritance of type.

## Interface Inheritance

An interface may extend multiple interfaces.

```java
interface SmartDevice extends Printable, Scannable {
    void connect();
}
```

An interface uses `extends`, while a class uses `implements`.

## Default Methods

Default methods allow interfaces to add behavior without immediately breaking existing implementations.

```java
interface NotificationService {

    void send(String message);

    default void log(String message) {
        System.out.println(message);
    }
}
```

Default methods support interface evolution but should not contain excessive business logic.

## Default-Method Conflict

If two interfaces provide the same default method, the class must resolve the conflict.

```java
interface First {
    default void display() {
        System.out.println("First");
    }
}

interface Second {
    default void display() {
        System.out.println("Second");
    }
}

class Example implements First, Second {

    @Override
    public void display() {
        First.super.display();
    }
}
```

## Conflict-Resolution Rules

General rules:

1. Class methods have priority over interface default methods.
2. A more specific child interface has priority.
3. Unrelated conflicting defaults must be explicitly resolved.

## Static Interface Methods

Static methods belong to the interface.

```java
PaymentProcessor.isValidAmount(100);
```

They are not inherited by implementing classes and should be called using the interface name.

## Callback Using an Interface

A callback allows one object to supply behavior that another object executes later.

```java
interface TaskCallback {
    void onComplete(String result);
}
```

```java
class TaskExecutor {

    void execute(TaskCallback callback) {
        String result = "Completed";
        callback.onComplete(result);
    }
}
```

```java
TaskExecutor executor = new TaskExecutor();

executor.execute(result ->
        System.out.println(result));
```

The caller controls what happens after task completion.

## Functional Interface

A functional interface contains exactly one abstract method.

```java
@FunctionalInterface
interface Calculator {
    int calculate(int first, int second);
}
```

It may still contain:

- Default methods
- Static methods
- Methods inherited from `Object`

Functional interfaces can be implemented using lambda expressions.

## Abstract Class vs Interface

Use an interface when:

- Unrelated classes need the same contract.
- Multiple contracts must be implemented.
- A capability or role is being modelled.
- Loose coupling is required.

Use an abstract class when:

- Related classes share state.
- Constructors are required.
- Common protected implementation is needed.
- A strong parent-child relationship exists.

## Marker Interface

A marker interface contains no methods and marks a class with specific metadata or capability.

Examples include:

- `Serializable`
- `Cloneable`

Annotations are often preferred for new metadata designs, but marker interfaces can participate in type relationships.

## Design Guidelines

- Keep interfaces focused.
- Depend on interfaces, not concrete classes.
- Avoid large interfaces containing unrelated methods.
- Use constructor injection for interface dependencies.
- Do not add default methods only to avoid creating a better abstraction.
- Name interfaces by capability or responsibility.

## Summary

- Interfaces define contracts.
- A class can implement multiple interfaces.
- Java 8 interfaces support default and static methods.
- Interface fields are public static final.
- Interface abstract methods are public.
- Interfaces enable callbacks, functional programming, and loose coupling.
- Conflicting default methods must be explicitly resolved.
