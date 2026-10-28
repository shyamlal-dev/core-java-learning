# Association, Aggregation, and Composition Assignments

## Coding Questions

### 1. Model a University

Create:

- University
- Department
- Professor
- Student
- Address

### Requirements

Identify and implement:

- One-to-one association
- One-to-many association
- Many-to-many association
- Aggregation
- Composition

Document the lifecycle assumptions.

---

### 2. Design an Order Model

Create:

- Order
- Order item
- Product
- Customer

### Requirements

- Model order items using composition.
- Associate the order with a customer.
- Associate each order item with a product.
- Protect the internal item collection.
- Prevent invalid quantities.

---

### 3. Model Department and Employees

Create a department containing employees.

### Requirements

- Employees must be able to exist independently.
- Prevent external modification of the internal employee collection.
- Support employee addition and removal.
- Prevent duplicate employees.
- Explain why the relationship is aggregation.

---

### 4. Model House and Rooms

Create a house that owns rooms.

### Requirements

- Rooms should be created and managed by the house.
- Do not expose mutable room collections.
- Do not allow one room to belong to multiple houses.
- Explain why the relationship is composition.

---

### 5. Refactor Incorrect Inheritance

A `Car` class extends an `Engine` class only to use engine methods.

### Requirements

- Replace inheritance with composition.
- Define an engine abstraction.
- Inject an engine into the car.
- Support petrol and electric engines.
- Explain why the new relationship is correct.

---

### 6. Build a Team Model

Create:

- Team
- Player
- Coach

### Requirements

- Decide whether relationships represent association or aggregation.
- Document lifecycle decisions.
- Avoid unnecessary bidirectional references.
- Protect all internal collections.

---

### 7. Maintain a Bidirectional Relationship

Create department and employee objects that reference each other.

### Requirements

- Keep both sides consistent when adding an employee.
- Keep both sides consistent when removing an employee.
- Prevent infinite recursion in `toString()`.
- Explain whether both directions are actually necessary.

---

## Interview Questions and Answers

### 1. What is association?

Association is a general relationship where one object knows about, uses, or communicates with another object.

### 2. What is aggregation?

Aggregation is a weak HAS-A relationship where the contained object can exist independently of the container.

### 3. What is composition?

Composition is a strong HAS-A relationship where the container owns and manages the contained object's lifecycle.

### 4. What is the main difference between aggregation and composition?

The primary difference is ownership and lifecycle dependency.

### 5. Does Java provide special keywords for aggregation and composition?

No. They are design relationships expressed through object references and lifecycle decisions.

### 6. Can an aggregated object be shared?

Yes. Since it has an independent lifecycle, multiple objects may reference it when the design permits.

### 7. Should a composed object normally be shared between owners?

Usually no. A composed object normally belongs exclusively to its owner.

### 8. What does composition over inheritance mean?

It means behavior should often be reused by containing and delegating to objects rather than creating unnecessary inheritance hierarchies.

### 9. When should inheritance be selected over composition?

Use inheritance when a genuine IS-A relationship and behavioral substitutability exist.

### 10. Why is composition more flexible?

Dependencies and behavior can be replaced without changing the class hierarchy.

### 11. What is a bidirectional association?

It is a relationship where both objects hold references to each other.

### 12. What problems can bidirectional relationships cause?

They may create inconsistent updates, recursive output, serialization cycles, and additional coupling.
