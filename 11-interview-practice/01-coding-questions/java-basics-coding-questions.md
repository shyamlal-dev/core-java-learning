# Java Basics Coding Questions

These questions test Java fundamentals, problem-solving skills, edge-case handling, and code quality.

## 1. Find the Second Largest Distinct Element

Given an integer array, find the second-largest distinct element.

### Requirements

- Do not sort the array.
- Traverse the array only once.
- Handle duplicate and negative values.
- Define behavior when the second-largest element does not exist.

---

## 2. Move All Zeros to the End

Move all zero values to the end of an array while preserving the relative order of non-zero elements.

### Requirements

- Modify the original array.
- Do not use an additional array.
- Target time complexity: `O(n)`.
- Target space complexity: `O(1)`.

---

## 3. Find the Missing Number

An array contains distinct numbers from `1` to `n`, with one number missing. Find the missing number.

### Requirements

- Implement an arithmetic solution.
- Avoid integer overflow.
- Implement an XOR-based solution.
- Compare both approaches.

---

## 4. Rotate an Array

Rotate an integer array to the right by `k` positions.

### Requirements

- Handle `k` greater than the array length.
- Implement an in-place solution.
- Target time complexity: `O(n)`.
- Target space complexity: `O(1)`.

---

## 5. Find Duplicate Elements

Find all duplicate elements in an integer array.

### Requirements

- Return each duplicate only once.
- Preserve the order in which duplicates are discovered.
- Provide solutions with and without an additional collection.
- Handle null and empty arrays.

---

## 6. Find the First Non-Repeating Character

Find the first character that occurs exactly once in a string.

### Requirements

- Preserve character order.
- Avoid repeatedly scanning the complete string.
- Return a clear result when no unique character exists.
- Handle null and empty strings.

---

## 7. Check Whether Two Strings Are Anagrams

Determine whether two strings are anagrams.

### Requirements

- Ignore character case and spaces.
- Implement a sorting-based solution.
- Implement a frequency-based solution.
- Compare the time and space complexity.

---

## 8. Compress a String

Implement basic string compression.

### Example

```text
Input:  aaabbccccd
Output: a3b2c4d1
```

### Requirements

- Use `StringBuilder`.
- Return the original string if compression does not reduce its size.
- Handle null and empty input.
- Analyze the time and space complexity.

---

## 9. Reverse Words in a Sentence

Reverse the order of words without reversing the individual words.

### Example

```text
Input:  Java is easy to learn
Output: learn to easy is Java
```

### Requirements

- Remove unnecessary spaces.
- Handle leading, trailing, and multiple spaces.
- Do not directly reverse the complete string.
- Preserve the characters of individual words.

---

## 10. Remove Duplicate Characters

Remove duplicate characters from a string while preserving the first occurrence of every character.

### Example

```text
Input:  programming
Output: progamin
```

### Requirements

- Preserve insertion order.
- Implement one solution using a collection.
- Implement another solution without a collection.
- Handle spaces and special characters.

---

## 11. Rotate a Matrix

Rotate a square matrix by 90 degrees clockwise.

### Requirements

- Implement an in-place solution.
- Do not create another matrix.
- Use transpose and row-reversal operations.
- Handle null and empty matrices safely.

---

## 12. Validate Balanced Brackets

Determine whether an expression containing `()`, `{}`, and `[]` has balanced brackets.

### Requirements

- Reject incorrectly ordered brackets.
- Ignore non-bracket characters.
- Target time complexity: `O(n)`.
- Handle an empty expression.

---

## 13. Find the Maximum Sum Subarray

Find the contiguous subarray having the maximum sum.

### Requirements

- Implement Kadane's algorithm.
- Handle arrays containing only negative values.
- Return the maximum sum.
- Also return the starting and ending indexes.
- Target time complexity: `O(n)`.

---

## 14. Find the Longest Common Prefix

Find the longest common prefix among an array of strings.

### Example

```text
Input:  ["flower", "flow", "flight"]
Output: "fl"
```

### Requirements

- Return an empty string when no common prefix exists.
- Handle null and empty input.
- Avoid unnecessary string creation.
- Explain the time complexity.

---

## 15. Merge Two Sorted Arrays

Merge two sorted integer arrays into one sorted array.

### Requirements

- Implement a solution using an additional array.
- Implement an in-place solution when the first array has enough capacity.
- Avoid sorting the merged result again.
- Target time complexity: `O(m + n)`.

---

## 16. Find the Majority Element

Find the element that appears more than `n / 2` times in an array.

### Requirements

- Implement a frequency-based solution.
- Implement the Boyer-Moore Voting Algorithm.
- Verify that the candidate is actually a majority element.
- Handle the case where no majority element exists.

---

## 17. Check Whether a Number Is Palindrome

Determine whether an integer is a palindrome.

### Requirements

- Do not convert the number into a string.
- Handle negative numbers.
- Avoid integer overflow while reversing digits.
- Explain the time and space complexity.

---

## 18. Create a Command-Line Calculator

Create a calculator supporting:

- Addition
- Subtraction
- Multiplication
- Division
- Remainder

### Requirements

- Use separate methods for operations.
- Handle division by zero.
- Validate unsupported operators.
- Avoid unnecessary nested conditions.
- Keep input handling separate from calculation logic.