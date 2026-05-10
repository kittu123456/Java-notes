# 📌 Exception Handling in Java

## 🔹 What is an Exception?

An **exception** is an abnormal event that occurs during program execution and disrupts the normal flow of the program.

* If not handled → program may terminate abruptly
* If handled → program continues normally

---

## 🔹 Types of Exceptions

### 1) Checked Exceptions (Compile-time)

* Checked by the compiler
* Must be handled using `try-catch` or `throws`
* Occur at runtime, but compiler enforces handling

**Examples:**

* `IOException`
* `SQLException`

---

### 2) Unchecked Exceptions (Runtime)

* Occur during execution
* Not checked by compiler
* Usually caused by programming mistakes

**Examples:**

* `NullPointerException`
* `ArithmeticException`
* `ArrayIndexOutOfBoundsException`

---

### 3) Errors (Not Exceptions)

* Caused by JVM
* Not recoverable

**Examples:**

* `OutOfMemoryError`
* `StackOverflowError`

---

## 🔹 Exception Hierarchy

```text
Throwable
│
├── Error
│
└── Exception
     │
     ├── Checked Exceptions
     │
     └── RuntimeException (Unchecked)
```

---

## 🔹 Exception Handling Keywords

### 1) `try`

```java
try {
    int result = 10 / 0;
}
```

---

### 2) `catch`

```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero");
}
```

---

### 3) `finally`

```java
finally {
    System.out.println("Always executes");
}
```

---

### 4) `throw`

```java
throw new IllegalArgumentException("Invalid input");
```

---

### 5) `throws`

```java
void readFile() throws IOException {
    // risky code
}
```

---

## 🔹 Multiple Catch Blocks

```java
try {
    int a = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Arithmetic error");
} catch (Exception e) {
    System.out.println("General error");
}
```

✔ Always write **child → parent order**

---

## 🔹 try-with-resources (Best Practice)

```java
import java.io.*;

try (BufferedReader br = new BufferedReader(new FileReader("test.txt"))) {
    System.out.println(br.readLine());
} catch (IOException e) {
    System.out.println("Error reading file");
}
```

---

## 🔹 Custom Exceptions

### ✔ Creating Custom Exception

```java
class InvalidAgeException extends RuntimeException {
    public InvalidAgeException(String message) {
        super(message);
    }
}
```

---

### ✔ Using Custom Exception

```java
if (age < 0) {
    throw new InvalidAgeException("Age cannot be negative");
}
```

---

## 🔹 Best Practices

* ✔ Use specific exceptions instead of generic `Exception`
* ✔ Prefer unchecked exceptions for business logic
* ✔ Always provide meaningful messages
* ✔ Use try-with-resources for resource handling
* ✔ Maintain proper exception hierarchy
* ❌ Do not use empty `catch` blocks
* ❌ Do not use exceptions for normal flow

---

## 🔹 Common Mistakes

* Catching `Exception` everywhere
* Wrong order of catch blocks
* Ignoring exceptions
* Not preserving original exception

---

## 📌 Note

When `System.exit()` is called, the `finally` block **will not execute**.
