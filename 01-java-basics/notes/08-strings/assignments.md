# Strings Assignments

## Coding Questions

### 1. Find the First Non-Repeating Character

Find the first character that occurs exactly once.

### Requirements

- Preserve character order.
- Avoid repeatedly scanning the complete string.
- Return a clear result when no unique character exists.
- Define case sensitivity.

---

### 2. Check Whether Two Strings Are Anagrams

Determine whether two strings are anagrams.

### Requirements

- Ignore case and spaces.
- Implement a sorting-based solution.
- Implement a frequency-based solution.
- Compare the complexity of both solutions.

---

### 3. Compress a String

Compress consecutive repeated characters.

### Example

```text
Input:  aaabbccccd
Output: a3b2c4d1
```

### Requirements

- Use `StringBuilder`.
- Return the original string if compression does not reduce its length.
- Handle null and empty values.

---

### 4. Reverse Words in a Sentence

Reverse word order without reversing individual words.

### Example

```text
Input:  Java is easy to learn
Output: learn to easy is Java
```

### Requirements

- Remove extra spaces.
- Handle leading and trailing spaces.
- Avoid directly reversing the complete character sequence.

---

### 5. Find the Longest Substring Without Repeating Characters

Return the length and content of the longest substring containing distinct characters.

### Requirements

- Use a sliding-window approach.
- Target time complexity: `O(n)`.
- Define behavior for an empty string.

---

### 6. Group Anagrams

Group words that are anagrams.

### Example

```text
Input:  ["eat", "tea", "tan", "ate", "nat", "bat"]
Output: [["eat", "tea", "ate"], ["tan", "nat"], ["bat"]]
```

### Requirements

- Preserve encounter order.
- Handle duplicate words.
- Use a stable normalized key.

---

### 7. Validate a Palindrome

Determine whether a string is a palindrome.

### Requirements

- Ignore case.
- Ignore spaces and punctuation.
- Do not create multiple unnecessary intermediate strings.
- Handle Unicode considerations as an optional extension.

---

### 8. Implement Basic String Matching

Find the first index of a pattern inside a source string.

### Requirements

- Do not use `String.indexOf()`.
- Implement a straightforward solution.
- Analyze time complexity.
- Optionally implement KMP after the basic solution.

---

### 9. Count Unicode Code Points

Count:

- UTF-16 code units
- Unicode code points

Use a string containing a character represented by a surrogate pair and explain why the counts may differ.

---

## Interview Questions and Answers

### 1. Why is String immutable?

Immutability enables safe pooling, thread safety, stable hash codes, security, and reliable use as map keys.

### 2. What is the String pool?

It is a JVM-managed pool that reuses canonical String instances, especially string literals, to reduce duplicate objects.

### 3. What is the difference between `==` and `equals()` for Strings?

`==` compares object references. `equals()` compares character content.

### 4. What is the difference between String, StringBuilder, and StringBuffer?

- String is immutable.
- StringBuilder is mutable and not synchronized.
- StringBuffer is mutable and synchronized.

### 5. Why is StringBuilder preferred for repeated concatenation?

String concatenation may create multiple intermediate String objects. StringBuilder modifies an internal buffer and is generally more efficient.

### 6. What does `intern()` do?

It returns the canonical pooled representation of a String.

### 7. Why is String suitable as a HashMap key?

String is immutable and implements consistent `equals()` and `hashCode()`. Its content and hash code do not change after creation.

### 8. What is the difference between `isEmpty()` and `isBlank()`?

`isEmpty()` checks whether length is zero. `isBlank()` checks whether the string is empty or contains only whitespace.

### 9. Does one char always represent one visible Unicode character?

No. A `char` represents one UTF-16 code unit. Some Unicode characters require two code units called a surrogate pair.