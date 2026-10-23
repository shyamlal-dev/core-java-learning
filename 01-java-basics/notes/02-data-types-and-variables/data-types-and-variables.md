# Data Types and Variables

## Variables

A variable is a named memory location used to store a value.

```java
int age = 25;
```

- `int`: Data type
- `age`: Variable name
- `25`: Initial value

## Variable Declaration and Initialization

```java
int count;      // Declaration
count = 10;     // Initialization

int total = 20; // Declaration and initialization
```

A local variable must be initialized before use.

## Types of Variables

### Local Variable

Declared inside a method, constructor, or block.

```java
void display() {
    int count = 10;
}
```

- No default value
- Stored in the current stack frame
- Exists until the block execution completes

### Instance Variable

Declared inside a class but outside methods and without `static`.

```java
class Employee {
    int id;
}
```

- Belongs to an object
- Gets a default value
- Stored as part of the object

### Static Variable

Declared using `static`.

```java
class Employee {
    static String company = "ABC";
}
```

- Belongs to the class
- Shared by all instances
- Initialized when the class is initialized

## Primitive Data Types

| Type | Size | Default Value | Typical Use |
|---|---:|---|---|
| `byte` | 8-bit | `0` | Small integer values |
| `short` | 16-bit | `0` | Limited-range integers |
| `int` | 32-bit | `0` | Default integer type |
| `long` | 64-bit | `0L` | Large integer values |
| `float` | 32-bit | `0.0f` | Decimal values with lower precision |
| `double` | 64-bit | `0.0d` | Default decimal type |
| `char` | 16-bit | `'\u0000'` | UTF-16 code unit |
| `boolean` | JVM-dependent | `false` | Logical values |

> Default values apply to instance and static variables, not local variables.

## Reference Data Types

Reference variables store a reference to an object.

Examples:

- Classes
- Interfaces
- Arrays
- Enums
- Records

```java
String name = "Java";
int[] numbers = {1, 2, 3};
```

The default value of an instance or static reference variable is `null`.

## Primitive vs Reference Types

### Primitive Type

- Stores the actual value
- Has a fixed type and size
- Cannot be `null`
- Does not provide methods

### Reference Type

- Stores a reference to an object
- Can be `null`
- Provides access to object methods and fields
- Object memory is managed by the JVM

## Literals

```java
int decimal = 100;
int binary = 0b1100100;
int hexadecimal = 0x64;
long population = 8_000_000_000L;
float rate = 10.5F;
char grade = 'A';
boolean active = true;
```

Underscores improve numeric literal readability but do not affect the value.

## Type Casting

### Widening Casting

A smaller compatible type is converted into a larger type automatically.

```java
int number = 100;
long value = number;
```

```text
byte → short → int → long → float → double
          char → int
```

### Narrowing Casting

A larger type is explicitly converted into a smaller type.

```java
double price = 99.99;
int value = (int) price;
```

Narrowing may cause:

- Data loss
- Precision loss
- Overflow

## Integer Promotion

Arithmetic operations on `byte`, `short`, and `char` generally produce an `int`.

```java
byte first = 10;
byte second = 20;
int result = first + second;
```

## `var`

`var` allows local variable type inference.

```java
var message = "Hello";
var count = 10;
```

Important rules:

- Allowed only for local variables
- Must be initialized during declaration
- Java remains statically typed
- Cannot be initialized with only `null`
- Should not reduce readability

## Summary

- Java has primitive and reference data types.
- Local variables do not receive default values.
- Instance variables belong to objects.
- Static variables belong to classes.
- Narrowing conversions may lose data.
- Arithmetic on smaller integer types usually produces `int`.