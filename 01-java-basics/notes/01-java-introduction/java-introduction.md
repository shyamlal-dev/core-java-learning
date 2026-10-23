# Java Introduction

## What is Java?

Java is a high-level, class-based, object-oriented programming language.

Java source code is compiled into platform-independent bytecode, which runs on the Java Virtual Machine.

```text
Source Code (.java)
        ↓ javac
Bytecode (.class)
        ↓ JVM
Machine-Specific Instructions
```

## Important Features

- Platform independent
- Object-oriented
- Strongly typed
- Automatic memory management
- Exception handling
- Multithreading support
- Rich standard library
- Architecture neutral

## Platform Independence

Java follows the principle:

```text
Write Once, Run Anywhere
```

The Java compiler generates bytecode instead of platform-specific machine code. Any system with a compatible JVM can execute this bytecode.

## JDK, JRE, and JVM

### JVM

The Java Virtual Machine executes Java bytecode.

Main responsibilities:

- Loading classes
- Verifying bytecode
- Managing runtime memory
- Executing bytecode
- Performing garbage collection

### JRE

The Java Runtime Environment provides the environment required to run Java applications.

```text
JRE = JVM + Runtime Libraries
```

### JDK

The Java Development Kit provides tools required to develop and run Java programs.

```text
JDK = JRE + Development Tools
```

Important JDK tools:

- `javac`: Compiles Java source code
- `java`: Runs Java applications
- `javadoc`: Generates documentation
- `jar`: Creates and manages JAR files
- `jdb`: Java debugger

## Compilation and Execution

Consider the following file:

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, Java");
    }
}
```

Compile:

```bash
javac Main.java
```

Run:

```bash
java Main
```

## Main Method

```java
public static void main(String[] args)
```

- `public`: JVM can access the method.
- `static`: JVM can call it without creating an object.
- `void`: It does not return a value.
- `main`: Standard application entry-point name.
- `String[] args`: Stores command-line arguments.

## Java is Not Completely Object-Oriented

Java supports primitive data types such as:

```text
byte, short, int, long, float, double, char, boolean
```

Primitive values are not objects. Therefore, Java is object-oriented but not purely object-oriented.

## JIT Compiler

The Just-In-Time compiler is part of the JVM execution engine.

Frequently executed bytecode is compiled into native machine code at runtime. This improves application performance by avoiding repeated bytecode interpretation.

## Summary

- Java source code is compiled into bytecode.
- JVM executes bytecode on a specific platform.
- JDK is used for development.
- JRE provides the runtime environment.
- JIT improves runtime performance.