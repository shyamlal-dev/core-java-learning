# Encapsulation Assignments

## Coding Questions

### 1. Design an Encapsulated Bank Account

Support:

- Deposit
- Withdrawal
- Balance enquiry
- Transaction history

### Requirements

- Keep balance private.
- Prevent invalid transactions.
- Do not expose mutable transaction history.
- Use meaningful methods instead of a balance setter.
- Preserve account invariants.

---

### 2. Refactor an Anemic Employee Class

An employee class contains public fields and unrestricted setters.

Refactor it to enforce:

- Positive employee ID
- Non-blank name
- Non-negative salary
- Controlled salary increments

### Requirements

- Remove unnecessary setters.
- Add meaningful behavior.
- Reject invalid state changes.

---

### 3. Protect a Mutable Collection

Create a `Team` class containing members.

### Requirements

- Prevent callers from modifying the internal member list.
- Provide methods for adding and removing valid members.
- Prevent duplicate members.
- Return a read-only snapshot or view.

---

### 4. Create an Immutable Person

Create an immutable `Person` containing:

- Name
- Date of birth
- Address
- List of skills

### Requirements

- Defensively copy mutable inputs.
- Do not expose mutable internal state.
- Validate mandatory fields.
- Implement logical equality.

---

### 5. Model Order Status Transitions

Create an `Order` with statuses:

```text
CREATED -> PAID -> SHIPPED -> DELIVERED
```

### Requirements

- Prevent invalid transitions.
- Do not expose a general `setStatus()` method.
- Provide meaningful transition methods.
- Prevent changing a delivered order.

---

### 6. Encapsulate a Product Inventory

Create an inventory class supporting:

- Stock addition
- Stock reservation
- Stock release

### Requirements

- Stock must never become negative.
- Reject invalid quantities.
- Do not expose a stock setter.
- Keep reservation logic atomic at the object level.

---

## Interview Questions and Answers

### 1. What is encapsulation?

Encapsulation combines state and behavior inside a class and controls how external code accesses or modifies that state.

### 2. Is encapsulation the same as data hiding?

No. Data hiding restricts visibility. Encapsulation also protects object behavior and invariants.

### 3. Do private fields and public getters/setters guarantee encapsulation?

No. Unrestricted setters and mutable getters can still expose and corrupt object state.

### 4. What is an object invariant?

An invariant is a rule that must remain true for an object to stay valid.

### 5. How can collections be encapsulated?

Do not return the internal mutable collection directly. Return an immutable copy or provide focused modification methods.

### 6. What is the difference between encapsulation and abstraction?

Encapsulation controls access to internal state. Abstraction exposes essential behavior while hiding implementation details.

### 7. What is the difference between encapsulation and immutability?

Encapsulation permits controlled state changes. Immutability prevents state changes after object construction.

### 8. Why are meaningful methods better than generic setters?

Meaningful methods communicate intent, enforce business rules, and keep objects in a valid state.

### 9. Can encapsulation improve maintainability?

Yes. Internal implementation can change without affecting callers when a stable public contract is maintained.
