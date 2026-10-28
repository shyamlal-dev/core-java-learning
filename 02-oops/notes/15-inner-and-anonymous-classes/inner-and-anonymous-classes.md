# Inner and Anonymous Classes

A nested class is declared inside another class.

Java supports:

- Static nested class
- Member inner class
- Local inner class
- Anonymous inner class

Technically, the term inner class refers to non-static nested classes.

# Member Inner Class

A member inner class is declared inside another class without `static`.

```java
class Outer {

    private int value = 10;

    class Inner {

        void display() {
            System.out.println(value);
        }
    }
}
```

Create an inner-class object through an outer object:

```java
Outer outer = new Outer();
Outer.Inner inner = outer.new Inner();
inner.display();
```

A member inner-class object is associated with an outer-class object.

It can directly access outer instance members, including private members.

## Outer and Inner `this`

Inside the inner class:

```java
this
```

refers to the inner object.

Use:

```java
Outer.this
```

to refer to the enclosing outer object.

```java
class Outer {

    private int value = 10;

    class Inner {

        private int value = 20;

        void display() {
            System.out.println(this.value);
            System.out.println(Outer.this.value);
        }
    }
}
```

# Static Nested Class

A static nested class is declared using `static`.

```java
class Outer {

    static class Nested {

        void display() {
            System.out.println("Static nested class");
        }
    }
}
```

Create it without an outer object:

```java
Outer.Nested nested = new Outer.Nested();
```

A static nested class:

- Does not hold an implicit outer-object reference
- Cannot directly access outer instance members
- Can directly access outer static members
- Is often used to group helper types or builders

# Local Inner Class

A local inner class is declared inside a method or block.

```java
class ReportService {

    void generateReport() {

        class Formatter {

            String format(String value) {
                return value.toUpperCase();
            }
        }

        Formatter formatter = new Formatter();
        System.out.println(formatter.format("report"));
    }
}
```

Its scope is limited to the block where it is declared.

## Effectively Final Variables

A local inner class can access local variables only when they are final or effectively final.

```java
void display() {
    String message = "Hello";

    class Printer {
        void print() {
            System.out.println(message);
        }
    }
}
```

`message` is effectively final because it is not reassigned.

The compiler captures the value because local variables normally belong to a method stack frame that may end before the inner object is used.

# Anonymous Inner Class

An anonymous inner class creates an unnamed implementation at the point of use.

```java
interface Notification {

    void send(String message);
}
```

```java
Notification notification = new Notification() {

    @Override
    public void send(String message) {
        System.out.println(message);
    }
};
```

An anonymous class:

- Has no explicit class name
- Is declared and instantiated together
- Can implement an interface
- Can extend one class
- Cannot declare an explicit constructor
- May contain fields, methods, and initializer blocks

## Anonymous Class Extending a Class

```java
abstract class Task {

    abstract void execute();
}
```

```java
Task task = new Task() {

    @Override
    void execute() {
        System.out.println("Executing task");
    }
};
```

# Anonymous Class vs Lambda

A lambda can replace an anonymous class only when implementing a functional interface.

Anonymous class:

```java
Runnable task = new Runnable() {

    @Override
    public void run() {
        System.out.println("Running");
    }
};
```

Lambda:

```java
Runnable task = () -> System.out.println("Running");
```

## Important Differences

### Meaning of `this`

Inside an anonymous class, `this` refers to the anonymous-class object.

Inside a lambda, `this` refers to the enclosing instance.

### Scope

An anonymous class creates a new class scope.

A lambda follows the enclosing lexical scope.

### Supported Targets

An anonymous class may extend a class or implement an interface.

A lambda requires a functional interface.

### Members

An anonymous class may declare fields and additional methods.

A lambda only provides the functional method behavior.

## Callbacks

Anonymous classes were commonly used for callbacks before lambdas.

```java
button.onClick(new ClickListener() {

    @Override
    public void onClick() {
        System.out.println("Clicked");
    }
});
```

For functional interfaces, lambdas are normally more concise.

## Use Cases

### Member Inner Class

Use when a helper requires access to a particular outer object.

### Static Nested Class

Use when the nested type belongs conceptually to the outer class but does not require an outer instance.

### Local Inner Class

Use for small block-specific types requiring more structure than a lambda.

### Anonymous Inner Class

Use for one-time implementations requiring class-specific behavior or additional members.

## Memory Consideration

A non-static inner-class object normally holds an implicit reference to its outer object.

If the inner object lives longer than required, the outer object may also remain reachable.

Use a static nested class when outer-instance access is unnecessary.

## Common Mistakes

- Creating a member inner class without an outer object
- Calling every nested class an inner class
- Accessing outer instance state from a static nested class
- Modifying captured local variables
- Using anonymous classes when a lambda is clearer
- Assuming `this` has the same meaning in lambdas and anonymous classes
- Retaining an outer object unintentionally through an inner object

## Summary

- Member inner classes require an outer object.
- Static nested classes do not require an outer object.
- Local inner classes exist within method or block scope.
- Anonymous classes provide one-time unnamed implementations.
- Captured local variables must be final or effectively final.
- Lambdas can replace anonymous classes only for functional interfaces.
- `this` behaves differently in lambdas and anonymous classes.
