# `this` and `super` Assignments

## Coding Questions

### 1. Resolve Field Shadowing

Create an `Employee` class whose constructor parameters have the same names as its fields.

### Requirements

- Initialize fields using `this`.
- Demonstrate what happens when `this` is omitted.
- Keep fields private.

---

### 2. Implement Constructor Chaining

Create an employee class with constructors accepting:

- No arguments
- Employee ID
- Employee ID and name
- Employee ID, name, and department

### Requirements

- Use `this()` to avoid duplicated initialization.
- Ensure every constructor produces a valid object.
- Avoid recursive constructor calls.

---

### 3. Demonstrate Parent Constructor Calls

Create:

```text
Person -> Employee -> Developer
```

### Requirements

- Add parameterized constructors at each level.
- Use `super()` to pass required values.
- Print constructor execution order.
- Ensure each parent initializes its own fields.

---

### 4. Access Parent and Child Members

Create parent and child classes having:

- Fields with the same name
- Methods with the same signature

### Requirements

- Access the child field using `this`.
- Access the parent field using `super`.
- Invoke the child method normally.
- Invoke the parent method using `super`.
- Explain field hiding and method overriding.

---

### 5. Build a Fluent Query Builder

Create a small query-builder class supporting:

- `select()`
- `from()`
- `where()`
- `build()`

### Requirements

- Return `this` from appropriate methods.
- Keep internal state private.
- Prevent building an incomplete query.
- Do not expose mutable internal data.

---

### 6. Pass the Current Object

Create:

- `Employee`
- `EmployeeValidator`

Pass the current employee object to the validator using `this`.

### Requirements

- Do not publish `this` from the constructor.
- Perform validation only after object construction.
- Explain the risk of escaping `this`.

---

### 7. Access the Outer Object

Create an outer class and a member inner class containing fields with the same name.

### Requirements

- Access the inner field using `this`.
- Access the outer field using `OuterClass.this`.
- Explain which object each reference represents.

---

### 8. Identify Invalid Constructor Calls

Document why the following are invalid:

- `this()` after another statement
- `super()` after another statement
- Explicit `this()` and `super()` in one constructor
- Recursive constructor chaining
- Accessing `this` inside a static method

---

## Interview Questions and Answers

### 1. What does `this` represent?

`this` refers to the current object whose instance method or constructor is executing.

### 2. What does `super` represent?

`super` provides access to the immediate parent-class constructor and parent implementation of inherited members.

### 3. Is `super` a separate parent object?

No. Parent state is part of the same child object. `super` provides parent-level access.

### 4. What is the purpose of `this()`?

`this()` calls another constructor in the same class and supports constructor chaining.

### 5. What is the purpose of `super()`?

`super()` invokes a constructor of the immediate parent class.

### 6. Why must `this()` and `super()` be the first statement?

Object initialization must follow a defined constructor chain before the current constructor executes its remaining logic.

### 7. Can `this()` and `super()` be used together in one constructor?

They cannot both be called explicitly because both must be the first statement. A constructor called through `this()` eventually calls `super()`.

### 8. What happens when `super()` is not written?

The compiler attempts to insert a no-argument `super()` call.

### 9. Can `this` be used inside a static method?

No. A static method belongs to the class and has no current object.

### 10. Can `super` access private parent members?

No. Private members are not directly accessible in child classes.

### 11. How can an outer object be referenced from an inner class?

Use `OuterClass.this`.

### 12. What does escaping `this` mean?

It means exposing the current object before construction completes, which may allow other code to observe partially initialized state.
