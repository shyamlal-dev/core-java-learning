# Access Modifiers

Access modifiers control the visibility of classes, fields, constructors, and methods.

Java provides four access levels:

- `private`
- Package-private
- `protected`
- `public`

## Access Summary

### Private

Accessible only inside the declaring class.

```java
class BankAccount {
    private double balance;
}
```

Use private access for internal state and implementation details.

### Package-Private

When no access modifier is written, the member has package-private access.

```java
class OrderValidator {
}
```

```java
void validate() {
}
```

It is accessible only inside the same package.

Package-private access is sometimes called default access, but it is not related to the `default` keyword used by interface methods.

### Protected

Accessible:

- Inside the same package
- In subclasses outside the package through inheritance

```java
protected void validate() {
}
```

Protected access has important cross-package reference rules.

### Public

Accessible from every package where the declaring type itself is visible.

```java
public void process() {
}
```

Public members become part of the external API and should be exposed carefully.

## Access Matrix

```text
Access Level      Same Class   Same Package   Subclass Outside Package   Other Package
private               Yes          No                   No                    No
package-private       Yes          Yes                  No                    No
protected             Yes          Yes                  Yes                   No
public                Yes          Yes                  Yes                   Yes
```

## Top-Level Class Access

A top-level class can use only:

- `public`
- Package-private

A top-level class cannot be:

- `private`
- `protected`

```java
public class Employee {
}

class EmployeeValidator {
}
```

Nested classes may use all access modifiers.

## Protected Cross-Package Rule

Consider a parent class in one package:

```java
package parent;

public class Parent {
    protected int value = 10;
}
```

A subclass in another package can access the inherited member through the child object's inheritance context.

```java
package child;

class Child extends Parent {

    void display() {
        System.out.println(value);
        System.out.println(this.value);
    }
}
```

The subclass cannot generally use an arbitrary `Parent` reference to access the protected member outside the package.

```java
Parent parent = new Parent();
// parent.value; // Not allowed
```

## Overriding and Access Levels

An overriding method cannot reduce visibility.

Valid widening:

```text
protected -> public
package-private -> protected
package-private -> public
```

Invalid reduction:

```text
public -> protected
protected -> private
```

The child implementation must preserve the parent contract's accessibility.

## Constructor Access

Constructor visibility controls object creation.

### Public Constructor

Allows creation from any accessible package.

### Protected Constructor

Supports controlled subclass creation.

### Package-Private Constructor

Restricts object creation to the same package.

### Private Constructor

Prevents direct external object creation.

Common uses:

- Utility classes
- Factory methods
- Singleton implementations
- Controlled instance creation

## Access Modifiers and Encapsulation

Use the least permissive access level that supports the required design.

Recommended order of consideration:

```text
private -> package-private -> protected -> public
```

Do not make members public only for convenient testing.

## Public API Design

Once a member becomes public, callers may depend on it.

Public APIs should be:

- Small
- Stable
- Documented
- Validated
- Free from unnecessary implementation details

## Common Mistakes

- Confusing package-private with `protected`
- Assuming protected means subclass-only
- Making fields public
- Reducing visibility during overriding
- Exposing implementation classes publicly
- Making methods public without a real external use case
- Using protected mutable fields

## Summary

- Private access is limited to the declaring class.
- Package-private access is limited to the package.
- Protected access includes package access and controlled subclass access.
- Public access exposes a member everywhere the type is accessible.
- Top-level classes may be only public or package-private.
- Overriding methods cannot reduce visibility.
- Prefer the least permissive access level.
