# Object Class Assignments

## Coding Questions

### 1. Implement Employee Equality

Create an `Employee` class containing:

- Employee ID
- Name
- Department

### Requirements

- Define equality using employee ID.
- Override `equals()` and `hashCode()`.
- Handle null and unrelated objects.
- Test reflexivity, symmetry, transitivity, and consistency.

---

### 2. Test Equality in HashSet

Create multiple employee objects having the same employee ID.

### Requirements

- Add them to a `HashSet`.
- Test behavior before overriding equality methods.
- Override only `equals()` and observe the problem.
- Then properly override both `equals()` and `hashCode()`.

---

### 3. Use an Object as a HashMap Key

Create an `EmployeeKey` containing employee ID and department code.

### Requirements

- Implement stable equality and hash code.
- Use the object as a `HashMap` key.
- Demonstrate successful lookup using an equivalent key.
- Keep equality fields immutable.

---

### 4. Demonstrate Mutable-Key Failure

Create a mutable key and use it inside a `HashMap`.

### Requirements

- Insert the key into the map.
- Modify a field used by `hashCode()`.
- Attempt to retrieve the value.
- Explain why lookup may fail.
- Refactor the key as an immutable object.

---

### 5. Create a Safe `toString()`

Create a `UserAccount` containing:

- User ID
- Email
- Password
- Access token

### Requirements

- Override `toString()`.
- Include useful debugging information.
- Exclude password and access-token values.
- Keep the output readable.

---

### 6. Compare Shallow and Deep Copies

Create an employee containing a mutable address.

### Requirements

- Create a shallow copy.
- Modify the copied address.
- Observe the original object.
- Create an independent deep copy using a copy constructor.
- Explain the difference.

---

### 7. Design Equality for a Value Object

Create a `Money` value object containing:

- Amount
- Currency

### Requirements

- Make the class immutable.
- Implement `equals()`, `hashCode()`, and `toString()`.
- Define whether scale differences such as `10.0` and `10.00` are equal.
- Document the equality decision.

---

## Interview Questions and Answers

### 1. What is the Object class?

`Object` is the root class of the Java class hierarchy. Every class directly or indirectly extends it.

### 2. What does the default `equals()` implementation do?

It checks reference identity, similar to `==`.

### 3. What is the equals contract?

It requires reflexivity, symmetry, transitivity, consistency, and a false result when compared with null.

### 4. Why must hashCode be overridden with equals?

Equal objects must produce equal hash codes for correct behavior in hash-based collections.

### 5. Can unequal objects have the same hash code?

Yes. This is called a hash collision.

### 6. How do HashMap and HashSet use equals and hashCode?

They use `hashCode()` to locate a bucket and `equals()` to identify the matching key or element.

### 7. Why should hash-key fields not be mutable?

Changing equality fields after insertion may change the hash code and make the entry unreachable in its original bucket.

### 8. What is the difference between `==` and `equals()`?

`==` compares reference identity. `equals()` compares logical equality when overridden.

### 9. What does `toString()` return by default?

It returns a representation containing the runtime class name and an unsigned hexadecimal form of the object's hash value.

### 10. What type of copy does Object.clone usually create?

It creates a shallow field-by-field copy.

### 11. Why is Cloneable considered difficult to use?

It has an unusual contract, may expose shallow-copy problems, bypasses constructors, and requires exception handling.

### 12. Why should finalize not be used?

Its execution is unpredictable and deprecated. Resources should be managed using try-with-resources or explicit cleanup.

### 13. Can getClass be overridden?

No. `getClass()` is final.

### 14. What can break equality in an inheritance hierarchy?

Additional child state may violate symmetry or transitivity between parent and child objects.
