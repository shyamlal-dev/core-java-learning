# Java Operators

Operators perform operations on values and variables.

## Arithmetic Operators

```java
int sum = 10 + 5;
int difference = 10 - 5;
int product = 10 * 5;
int quotient = 10 / 5;
int remainder = 10 % 3;
```

For integer operands, division returns an integer result.

```java
int result = 5 / 2; // 2
```

## Unary Operators

```java
int number = 10;

number++;
number--;
int negative = -number;
boolean active = true;
boolean inactive = !active;
```

### Prefix vs Postfix

```java
int value = 5;

int first = ++value;  // value = 6, first = 6
int second = value++; // second = 6, value = 7
```

Avoid complex expressions containing multiple increment operators.

## Relational Operators

```java
age >= 18
salary < limit
first == second
first != second
```

Relational operators return a boolean value.

## Logical Operators

```java
boolean eligible = age >= 18 && active;
boolean allowed = admin || manager;
boolean disabled = !active;
```

### Short-Circuit Evaluation

`&&` stops when the left operand is `false`.

`||` stops when the left operand is `true`.

```java
if (user != null && user.isActive()) {
    // Safe access
}
```

## Bitwise Operators

```java
a & b
a | b
a ^ b
~a
```

They operate on the binary representation of integral values.

Common use cases:

- Flags
- Masks
- Low-level protocols
- Permission combinations
- XOR-based algorithms

## Shift Operators

```java
number << 1
number >> 1
number >>> 1
```

- `<<`: Left shift
- `>>`: Signed right shift
- `>>>`: Unsigned right shift

The actual arithmetic meaning depends on overflow and the sign of the value.

## Assignment Operators

```java
value = 10;
value += 5;
value -= 2;
value *= 3;
value /= 2;
value %= 4;
```

Compound assignment includes an implicit cast.

```java
byte value = 10;
value += 5; // Compiles
```

The following requires explicit casting:

```java
value = (byte) (value + 5);
```

## Ternary Operator

```java
String result = age >= 18 ? "Adult" : "Minor";
```

Use the ternary operator for simple conditional expressions. Avoid deeply nested ternary expressions.

## `==` with Primitive and Reference Types

For primitives, `==` compares values.

```java
int first = 10;
int second = 10;
boolean same = first == second;
```

For references, `==` compares reference identity.

```java
String first = new String("Java");
String second = new String("Java");

boolean sameReference = first == second;
boolean sameValue = first.equals(second);
```

## Operator Precedence

Precedence decides which operation is evaluated first.

```java
int result = 2 + 3 * 4; // 14
```

Prefer parentheses when an expression is not immediately clear.

```java
int result = 2 + (3 * 4);
```

## Summary

- Integer division removes the fractional part.
- `&&` and `||` use short-circuit evaluation.
- `==` compares reference identity for objects.
- `equals()` commonly compares logical equality.
- Compound assignment may perform implicit narrowing.
- Parentheses improve expression readability.