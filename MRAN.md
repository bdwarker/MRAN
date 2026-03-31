# MRAN — Mathematically Redefined Algorithmic Notation

---

## Table of Contents

1. [Philosophy](#philosophy)
2. [Program Structure](#program-structure)
3. [Keywords Reference](#keywords-reference)
4. [Data Types](#data-types)
5. [Variables — SET & COMPUTE](#variables)
6. [Input & Output](#input--output)
7. [Operators](#operators)
8. [Conditionals](#conditionals)
9. [Loops](#loops)
10. [Functions](#functions)
11. [Arrays & Lists](#arrays--lists)
12. [Error Handling](#error-handling)
13. [Comments](#comments)
14. [Complete Examples](#complete-examples)

---

## Philosophy

MRAN is a pseudocode notation standard designed to merge mathematical formalism and programming logic. It is:

- **Strict** — every construct has a defined, unambiguous syntax
- **Readable** — humans can follow it without programming knowledge
- **Mathematical** — borrows from set theory, logic, and formal notation
- **Language-agnostic** — not tied to any programming language
- **Minimal** — no unnecessary keywords; nothing defined unless needed

> MRAN is not a programming language. It is a notation system for expressing algorithms clearly and precisely.

---

## Program Structure

Every MRAN algorithm follows this top-level structure:

```
1) START
2) ...
3) ...
n) STOP
```

- All steps are **numbered with Arabic numerals** followed by `)` or `.`
- Sub-steps inside blocks use **Roman numerals** followed by `)` or `.`
- Further nesting uses **lowercase Roman numerals** followed by `)` or `.`
- `START` and `STOP` are mandatory

### Nesting Levels

| Level              | Numbering                                | Example         |
| ------------------ | ---------------------------------------- | --------------- |
| Top-level steps    | Arabic                                   | `1), 2), 3)`    |
| First sub-level    | Uppercase Roman                          | `I), II), III)` |
| Second sub-level   | Lowercase Roman                          | `i), ii), iii)` |
| Third sub-level    | English Alphabets                        | `a), b), c)`    |
| Fourth sub-level   | Greek Alphabets                          | `α), β), γ)`    |
| Further sub-levels | Use your own notation that's consistent. |                 |

---

## Keywords Reference

All keywords are written in **ALL CAPS**.

| Keyword          | Purpose                           |
| ---------------- | --------------------------------- |
| `START`          | Begin the algorithm               |
| `STOP`           | End the algorithm                 |
| `INPUT`          | Receive input values              |
| `OUTPUT`         | Produce output                    |
| `SET`            | Assign a value to a variable      |
| `COMPUTE`        | Perform a mathematical operation  |
| `IF`             | Conditional check                 |
| `ELSE IF`        | Secondary conditional check       |
| `ELSE`           | Fallback condition                |
| `THEN:`          | Opens a conditional or loop block |
| `FOR`            | Definite loop                     |
| `WHILE`          | Indefinite loop                   |
| `BREAK`          | Exit a loop immediately           |
| `CONTINUE`       | Skip to next loop iteration       |
| `DEFINE`         | Declare a function                |
| `CALL`           | Invoke a function                 |
| `RETURN`         | Return value(s) from a function   |
| `TRY:`           | Attempt a block of steps          |
| `AND`            | Logical AND                       |
| `OR`             | Logical OR                        |
| `NOT`            | Logical NOT                       |
| `TRUE` / `FALSE` | Boolean values                    |
| `NULL` / `φ`     | Empty or absent value             |

---

## Data Types

Data types are **optional** — only declare them when absolutely necessary for clarity.

Types are prefixed with `D_`:

| Type    | Keyword    |
| ------- | ---------- |
| Integer | `D_int`    |
| Float   | `D_float`  |
| String  | `D_string` |
| Boolean | `D_bool`   |
| Array   | `D_array`  |
| List    | `D_list`   |

### Type Casting

Type casting is **fully implicit**, that means: no keyword, no type declaration needed. The variable's existing type is simply overridden:

```
COMPUTE x = someInt
```

If `x` was previously defined as a float, it simply becomes the assigned value.

---

## Variables

### SET for Assignment

Use `SET` for assigning values (non-mathematical):

```
SET name = "User"
SET D_bool flag = TRUE
SET count = 0
SET x = NULL
```

### COMPUTE for Mathematical Operations

Use `COMPUTE` for expressions involving calculation:

```
COMPUTE result = b^2 - 4*a*c
COMPUTE D_float avg = (x + y) / 2
COMPUTE root = sqrt(discriminant)
```

---

## Input & Output

```
INPUT var1, var2, var3
OUTPUT "Your result is {var1} and {var2}."
```

- `INPUT` accepts a comma-separated list of variable names
- `OUTPUT` accepts strings with `{}` interpolation (all strings behave like python f-strings)

> Variables used inside `{}` must be declared before the `OUTPUT` statement. If a variable hasn't been declared, MRAN treats it as a literal string, printing the `{name}` as-is rather than substituting its value.

---

## Operators

### Arithmetic

| Operation      | Accepted Notations               |
| -------------- | -------------------------------- |
| Addition       | `+`                              |
| Subtraction    | `-`                              |
| Multiplication | `*` or `×` or `·` (dot product)  |
| Division       | `/` or `÷` or `—` (fraction bar) |
| Exponentiation | `^` or superscript or `pow()`    |
| Modulo         | `mod` or `%`                     |
| Square Root    | `sqrt()` or `√`                  |
| Exponential    | `exp()` or `eⁿ`                  |
| Logarithm      | `log()` or `ln()`                |

> MRAN accepts all standard mathematical representations. Use whichever best suits the context.

### Comparison

| Operator | Meaning                  |
| -------- | ------------------------ |
| `=`      | Equal to                 |
| `≠`      | Not equal to             |
| `>`      | Greater than             |
| `<`      | Less than                |
| `≥`      | Greater than or equal to |
| `≤`      | Less than or equal to    |

### Logical

| Operator | Meaning     |
| -------- | ----------- |
| `AND`    | Logical AND |
| `OR`     | Logical OR  |
| `NOT`    | Logical NOT |

---

## Conditionals

```
IF condition THEN:
   I) task
   II) task
ELSE IF condition THEN:
   I) task
ELSE:
   I) task
```

- Every conditional block opens with `THEN:`
- `ELSE` does not require `THEN:` as it is unconditional and no condition end marker is required.
- Conditions use standard comparison and logical operators
- These share the same level and the same number.

---

## Loops

### FOR Loop

Three-part condition: `initializer, condition, increment`

```
FOR i = 0, i < n, i++ THEN:
   I) task
   II) task
```

### WHILE Loop

Single condition:

```
WHILE condition THEN:
   I) task
```

### Loop Control

```
BREAK
CONTINUE
```

Used inside loop blocks without numbering disruption.

---

## Functions

### Declaration

```
DEFINE functionName(param1, param2):
   I) task
   II) RETURN val1, val2
```

### Invocation

```
CALL functionName(arg1, arg2)
```

### Return

```
RETURN val1, val2, ...
```

Multiple return values are comma-separated.

---

## Arrays & Lists

### Declaration

```
SET D_array myArray = {1, 2, 3, 4, 5}
SET D_list myList = {1, "hello", 3.14}
```

### Set Builder Notation

```
SET D_array evens = {x | x ∈ ℕ, x mod 2 = 0}
SET D_array squares = {x^2 | x ∈ {1, 2, 3, 4, 5}}
```

### Indexing

```
myArray[i]
myList[0]
```

Zero-indexed, standard bracket notation.

---

## Error Handling

```
TRY:
   I) task to attempt
   II) task to attempt
IF error THEN:
   I) handle the error
   II) OUTPUT "Error: {error}"
```

- `TRY:` opens the attempt block
- `IF error THEN:` handles the caught error inline
- The `error` variable is automatically populated with the error caught if the `TRY` block fails
- No separate CATCH keyword needed
- Similar to if-else statements, these also share the same level and number

---

## Comments

Comments are **unnumbered** — any line without a step number is a comment:

```
This algorithm computes quadratic roots
1) START
2) INPUT a, b, c
Computing the discriminant first
3) COMPUTE d = b^2 - 4*a*c
4) STOP
```

---

## Complete Examples

### Example 1 — Quadratic Roots

```
Algorithm to compute roots of a quadratic equation ax^2 + bx + c = 0

1) START
2) INPUT a, b, c
3) COMPUTE d = sqrt(b^2 - 4*a*c)
4) IF d > 0 THEN:
      I) COMPUTE root1 = (-b + d) / 2*a
      II) COMPUTE root2 = (-b - d) / 2*a
      III) OUTPUT "Two real roots: {root1}, {root2}."
4) ELSE IF d = 0 THEN:
      I) COMPUTE root1 = -b / 2*a
      II) OUTPUT "One real root: {root1}."
4) ELSE:
      I) OUTPUT "No real roots exist."
5) STOP
```

---

### Example 2 — Factorial using Function

```
Algorithm to compute factorial of n

1) START
2) DEFINE factorial(n):
      I) IF n = 0 OR n = 1 THEN:
            i) RETURN 1
      II) RETURN n * CALL factorial(n - 1)
3) INPUT n
4) SET result = CALL factorial(n)
5) OUTPUT "Factorial of {n} is {result}."
6) STOP
```

---

### Example 3 — Linear Search

```
Algorithm to search for a target in an array

1) START
2) INPUT myArray, target
3) SET found = FALSE
4) FOR i = 0, i < myArray.length, i++ THEN:
      I) IF myArray[i] = target THEN:
            i) SET found = TRUE
            ii) OUTPUT "Found {target} at index {i}."
            iii) BREAK
5) IF found = FALSE THEN:
      I) OUTPUT "{target} not found in array."
6) STOP
```

---

### Example 4 — Safe Division with Error Handling

```
Algorithm to safely divide two numbers

1) START
2) INPUT a, b
3) TRY:
      I) IF b = 0 THEN:
            i) OUTPUT "Error: Division by zero."
            ii) STOP
      II) COMPUTE result = a / b
3) IF error THEN:
      I) OUTPUT "Unexpected error occurred."
4) OUTPUT "Result: {result}."
5) STOP
```

---

## Summary

MRAN provides a complete, self-consistent notation for expressing algorithms with:

- Mathematical precision
- Programming logic
- Human readability
- Minimal but strict syntax

---

*MRAN — Mathematically Redefined Algorithmic Notation*
