# Methods

A method is a named block of code that performs a specific operation.

## Method Syntax

```java
accessModifier returnType methodName(parameters) {
    // Method body
}
```

Example:

```java
public int add(int first, int second) {
    return first + second;
}
```

## Method Components

- Access modifier
- Optional non-access modifiers
- Return type
- Method name
- Parameter list
- Method body
- Optional declared exceptions

## Parameters and Arguments

Parameters appear in the method declaration.

Arguments are values supplied during invocation.

```java
int add(int first, int second) {
    return first + second;
}

int result = add(10, 20);
```

`first` and `second` are parameters. `10` and `20` are arguments.

## Java is Pass-by-Value

Java always passes a copy of the variable's value.

### Primitive Example

```java
void update(int number) {
    number = 100;
}
```

Changing the copied primitive value does not change the caller's variable.

### Reference Example

```java
void updateName(Employee employee) {
    employee.setName("Updated");
}
```

A copy of the reference is passed. Both references initially point to the same object, so object state can be modified.

Reassigning the parameter does not change the caller's reference:

```java
void replace(Employee employee) {
    employee = new Employee();
}
```

## Return Types

A method may return a value:

```java
int square(int number) {
    return number * number;
}
```

Or return nothing:

```java
void printMessage() {
    System.out.println("Hello");
}
```

## Method Overloading

Methods are overloaded when they have the same name but different parameter lists.

```java
int add(int first, int second) {
    return first + second;
}

double add(double first, double second) {
    return first + second;
}
```

Overloading cannot be based only on:

- Return type
- Parameter names
- Access modifier
- Declared exceptions

## Static and Instance Methods

### Static Method

Belongs to the class.

```java
Math.max(10, 20);
```

A static method cannot directly access instance members without an object.

### Instance Method

Belongs to an object and can access both instance and static members.

## Varargs

Varargs allow a variable number of arguments.

```java
int sum(int... values) {
    int total = 0;

    for (int value : values) {
        total += value;
    }

    return total;
}
```

Rules:

- Only one varargs parameter is allowed.
- It must be the last parameter.
- Internally, it is treated as an array.

## Recursion

A recursive method calls itself.

```java
long factorial(int number) {
    if (number <= 1) {
        return 1;
    }

    return number * factorial(number - 1);
}
```

A recursive solution needs:

- A base condition
- Progress toward the base condition

Deep recursion may cause `StackOverflowError`.

## Method Design Guidelines

- Keep methods focused on one responsibility.
- Prefer meaningful names.
- Keep parameter lists small.
- Avoid hidden side effects.
- Validate arguments at clear boundaries.
- Return meaningful results.
- Avoid boolean parameters when they make behavior unclear.
- Extract complex logic into focused helper methods.

## Summary

- Java is always pass-by-value.
- Overloading depends on the parameter list.
- Varargs are represented as arrays.
- Static methods belong to classes.
- Instance methods belong to objects.
- Recursion uses stack frames and requires a base condition.