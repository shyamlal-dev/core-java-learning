# Arrays Assignments

## Coding Questions

### 1. Find the Second Largest Distinct Element

Find the second-largest distinct value in an integer array.

### Requirements

- Do not sort the array.
- Traverse the array once.
- Handle duplicates and negative values.
- Define behavior when no second-largest value exists.

---

### 2. Move Zeros to the End

Move all zeros to the end while maintaining the relative order of non-zero elements.

### Requirements

- Modify the original array.
- Do not use another array.
- Target time complexity: `O(n)`.
- Target space complexity: `O(1)`.

---

### 3. Rotate an Array

Rotate an array to the right by `k` positions.

### Requirements

- Handle `k` greater than the array length.
- Use an in-place reversal-based approach.
- Target time complexity: `O(n)`.
- Target space complexity: `O(1)`.

---

### 4. Find the Missing Number

An array contains distinct values from `1` to `n`, with one value missing.

### Requirements

- Implement an XOR-based solution.
- Implement a mathematical solution without integer overflow.
- Compare both approaches.

---

### 5. Find the Maximum Sum Subarray

Find the contiguous subarray with the maximum sum.

### Requirements

- Use Kadane's algorithm.
- Handle arrays containing only negative values.
- Return the sum and subarray boundaries.
- Target time complexity: `O(n)`.

---

### 6. Merge Two Sorted Arrays

Merge two sorted arrays.

### Requirements

- Do not sort the merged result again.
- Target time complexity: `O(m + n)`.
- Implement an in-place version when the first array has sufficient capacity.

---

### 7. Rotate a Matrix

Rotate a square matrix 90 degrees clockwise.

### Requirements

- Perform the rotation in place.
- Use transpose and row reversal.
- Validate that the matrix is square.

---

### 8. Set Matrix Rows and Columns to Zero

If an element is zero, set its complete row and column to zero.

### Requirements

- First implement with additional storage.
- Then implement using constant extra space.
- Do not allow newly written zeros to affect later checks incorrectly.

---

### 9. Find an Element in a Sorted Matrix

Search for a target in a matrix where each row and column is sorted.

### Requirements

- Avoid scanning every element.
- Target time complexity: `O(rows + columns)`.
- Return row and column indexes.

---

## Interview Questions and Answers

### 1. Are arrays objects in Java?

Yes. Arrays are objects created at runtime and inherit methods from `Object`.

### 2. Why is an array length fixed?

The size is determined during array creation, and the allocated array object cannot be resized. A new array must be created for a different size.

### 3. What is array covariance?

It allows an array of a subtype to be assigned to a reference of a supertype array, such as assigning `String[]` to `Object[]`.

### 4. What is ArrayStoreException?

It occurs when an incompatible object is stored in an array whose runtime component type does not permit that object.

### 5. What is the difference between `length`, `length()`, and `size()`?

- Arrays use `length`.
- Strings use `length()`.
- Collections generally use `size()`.

### 6. What is a jagged array?

A jagged array is a multidimensional array whose inner arrays may have different lengths.

### 7. What is the difference between shallow and deep array copying?

A shallow copy duplicates the outer structure but shares nested referenced objects. A deep copy recursively copies nested mutable objects.

### 8. Why should arrays not be compared using `==`?

`==` compares array references. Use `Arrays.equals()` or `Arrays.deepEquals()` to compare contents.