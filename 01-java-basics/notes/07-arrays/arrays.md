# Arrays

An array stores a fixed number of elements of the same type.

## Declaration and Creation

```java
int[] numbers;
numbers = new int[5];
```

Combined form:

```java
int[] numbers = new int[5];
```

Array literal:

```java
int[] numbers = {10, 20, 30};
```

Prefer:

```java
int[] numbers;
```

Over:

```java
int numbers[];
```

## Array Properties

- Fixed length
- Zero-based indexing
- Stores elements of one declared type
- Can store primitive values or references
- Provides constant-time indexed access
- Arrays are objects in Java
- Length is available through the `length` field

```java
int size = numbers.length;
```

## Default Values

An array receives default element values.

```java
int[] values = new int[3];       // [0, 0, 0]
boolean[] flags = new boolean[2]; // [false, false]
String[] names = new String[2];   // [null, null]
```

## Accessing Elements

```java
int first = numbers[0];
numbers[1] = 50;
```

Invalid indexes cause `ArrayIndexOutOfBoundsException`.

## Traversing an Array

### Index-Based Loop

```java
for (int index = 0; index < numbers.length; index++) {
    System.out.println(numbers[index]);
}
```

Use when the index is required or elements must be replaced.

### Enhanced For Loop

```java
for (int number : numbers) {
    System.out.println(number);
}
```

Use for simple traversal.

## Multidimensional Arrays

Java multidimensional arrays are arrays containing other arrays.

```java
int[][] matrix = new int[3][4];
```

Rows may have different lengths.

```java
int[][] values = {
    {1, 2},
    {3, 4, 5}
};
```

This is called a jagged array.

## Arrays of Objects

```java
Employee[] employees = new Employee[3];
```

The array initially stores `null` references. Employee objects must be created separately.

## Copying Arrays

### `clone()`

```java
int[] copy = original.clone();
```

### `Arrays.copyOf()`

```java
int[] copy = Arrays.copyOf(original, original.length);
```

### `System.arraycopy()`

```java
System.arraycopy(source, 0, destination, 0, source.length);
```

For nested arrays, these operations produce a shallow copy of referenced inner arrays unless those arrays are copied separately.

## Utility Methods

```java
Arrays.sort(numbers);
Arrays.binarySearch(numbers, target);
Arrays.equals(first, second);
Arrays.fill(numbers, 0);
Arrays.toString(numbers);
Arrays.deepToString(matrix);
```

`Arrays.binarySearch()` requires sorted input for predictable results.

## Array Covariance

Java arrays are covariant:

```java
Object[] values = new String[2];
```

But storing an incompatible object fails at runtime:

```java
values[0] = 10; // ArrayStoreException
```

Generics use compile-time invariance to prevent similar unsafe operations.

## Complexity

| Operation | Complexity |
|---|---:|
| Access by index | `O(1)` |
| Search in unsorted array | `O(n)` |
| Insert or delete at end with free position | `O(1)` |
| Insert or delete in middle | `O(n)` |
| Sorting | Generally `O(n log n)` |

## Common Problems

- Off-by-one errors
- Accessing an invalid index
- Assuming object elements are initialized
- Comparing arrays using `==`
- Using binary search on unsorted data
- Confusing shallow and deep copy

## Summary

- Arrays have fixed length.
- Array indexes start at zero.
- Arrays receive default element values.
- Java supports jagged multidimensional arrays.
- Arrays are covariant and may produce runtime type errors.
- Use `Arrays.equals()` for content comparison.