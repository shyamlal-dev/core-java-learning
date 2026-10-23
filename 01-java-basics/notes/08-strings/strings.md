# Strings

A `String` represents an immutable sequence of characters.

```java
String language = "Java";
```

## String Immutability

Once created, a String object's value cannot be changed.

```java
String value = "Java";
value.concat(" Language");

System.out.println(value); // Java
```

A new value must be assigned:

```java
value = value.concat(" Language");
```

## Why Strings Are Immutable

Immutability supports:

- String pool reuse
- Thread safety
- Stable hash codes
- Security-sensitive values
- Safe use as map keys

## String Pool

String literals are stored in the string pool.

```java
String first = "Java";
String second = "Java";

System.out.println(first == second); // true
```

Objects explicitly created with `new` are separate objects:

```java
String third = new String("Java");

System.out.println(first == third);      // false
System.out.println(first.equals(third)); // true
```

## `==` vs `equals()`

- `==` compares references.
- `equals()` compares String contents.

Use `equals()` for logical comparison.

```java
"ACTIVE".equals(status);
```

This form is null-safe when the literal is known.

## Common String Methods

```java
value.length();
value.isEmpty();
value.isBlank();
value.charAt(0);
value.substring(1, 4);
value.contains("Java");
value.startsWith("J");
value.endsWith("a");
value.toLowerCase();
value.toUpperCase();
value.trim();
value.strip();
value.replace("a", "A");
value.split(",");
```

## `isEmpty()` vs `isBlank()`

```java
"".isEmpty();    // true
"   ".isEmpty(); // false
"   ".isBlank(); // true
```

`isBlank()` considers Unicode whitespace.

## `trim()` vs `strip()`

- `trim()` removes characters with values up to basic ASCII space.
- `strip()` uses Unicode-aware whitespace detection.

## String Concatenation

```java
String fullName = firstName + " " + lastName;
```

The compiler may optimize simple concatenation. Repeated concatenation inside loops creates unnecessary intermediate objects.

Avoid:

```java
String result = "";

for (String value : values) {
    result += value;
}
```

Prefer:

```java
StringBuilder builder = new StringBuilder();

for (String value : values) {
    builder.append(value);
}
```

## StringBuilder and StringBuffer

### StringBuilder

- Mutable
- Not synchronized
- Usually preferred for single-threaded string construction

### StringBuffer

- Mutable
- Synchronized
- Provides thread-safe individual operations
- Usually slower than StringBuilder

## `intern()`

`intern()` returns the pooled representation of a String.

```java
String value = new String("Java");
String pooled = value.intern();

System.out.println(pooled == "Java"); // true
```

Use it carefully. Manual interning is rarely needed in ordinary application code.

## String Hash Code

String caches its hash code after computation in typical JDK implementations. Immutability guarantees that the hash code does not change with String content.

This makes String suitable as a `HashMap` key.

## Character Representation

A Java `char` stores one UTF-16 code unit, not necessarily one complete Unicode character.

Some Unicode characters require a surrogate pair. For full Unicode handling, use code-point APIs such as:

```java
text.codePoints();
```

## Summary

- String objects are immutable.
- Literals are reused through the string pool.
- `==` checks reference identity.
- `equals()` checks content equality.
- Use StringBuilder for repeated string modifications.
- A `char` does not always represent a complete Unicode character.