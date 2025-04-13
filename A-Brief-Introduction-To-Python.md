# A Brief Introduction To Python

> _This guide is incomplete.  This message will be removed when a first draft is complete._

<!--BEGIN_TOC-->
- [A Brief Introduction To Python](#a-brief-introduction-to-python)
  - [1. Hello World](#1-hello-world)
    - [1.1. Simple Hello World](#11-simple-hello-world)
    - [1.2. More Structured Hello World](#12-more-structured-hello-world)
    - [1.3. Calling hello.py From Other Module](#13-calling-hellopy-from-other-module)
  - [2. Statement Organization And Whitespace](#2-statement-organization-and-whitespace)
    - [2.1. Indentation Is Syntax](#21-indentation-is-syntax)
    - [2.2. How Much Indentation?](#22-how-much-indentation)
    - [2.3. Colons Start Blocks](#23-colons-start-blocks)
    - [2.4. One Statement Per Line (Usually)](#24-one-statement-per-line-usually)
    - [2.5. Blank Lines And Grouping](#25-blank-lines-and-grouping)
    - [2.6. Gotchas](#26-gotchas)
  - [3. Comments](#3-comments)
    - [3.1. Single-Line Comments](#31-single-line-comments)
    - [3.2. Multi-Line Comments](#32-multi-line-comments)
    - [3.3. Comment Style](#33-comment-style)
  - [4. Naming Conventions](#4-naming-conventions)
    - [4.1. Summary Table](#41-summary-table)
    - [4.2. Variables And Functions](#42-variables-and-functions)
    - [4.3. Classes](#43-classes)
    - [4.4. Constants](#44-constants)
    - [4.5. Underscores and Visibility](#45-underscores-and-visibility)
    - [4.6. Modules And Packages](#46-modules-and-packages)
    - [4.7. Style Guidance](#47-style-guidance)
    - [4.8. Summary](#48-summary)
  - [5. Control Flow](#5-control-flow)
    - [5.1. if Statement](#51-if-statement)
    - [5.2. for Loop](#52-for-loop)
    - [5.3. while Loop](#53-while-loop)
    - [5.4. break And continue](#54-break-and-continue)
    - [5.5. No switch Or case Statement](#55-no-switch-or-case-statement)
    - [5.6. match Statement](#56-match-statement)
    - [5.7. else With Loops](#57-else-with-loops)
    - [5.8. Summary](#58-summary)
  - [6. Operators And Precedence](#6-operators-and-precedence)
    - [6.1. Arithmetic Operators](#61-arithmetic-operators)
    - [6.2. Comparison Operators](#62-comparison-operators)
    - [6.3. Logical Operators](#63-logical-operators)
    - [6.4. Identity Versus Equality](#64-identity-versus-equality)
    - [6.5. Boolean Values](#65-boolean-values)
    - [6.6. Bitwise Operators](#66-bitwise-operators)
    - [6.7. Assignment Expressions](#67-assignment-expressions)
    - [6.8. Operator Precedence](#68-operator-precedence)
    - [6.9. Summary](#69-summary)
  - [7. Core Data Structures](#7-core-data-structures)
<!--END_TOC-->

This is a quick introduction to Python for experienced programmers who are relatively new to Python.  This guide does not pretend to be a replacement for the full [Python Tutorial](https://docs.python.org/3/tutorial/index.html).  This guide aims to provide value through a curated selection of important knowledge that helps an experienced programmer get started quickly.

See also:  Full [Python documentation](https://docs.python.org).

It is assumed you already have Python installed and available at your shell prompt.

## 1. Hello World

### 1.1. Simple Hello World

This is the simplest possible hello world program:

```python
print("Hello, World!")
```

Save this as `hello_simple.py`.  In Python, any `.py` file is a _module_, which can be run or imported.  To run it:

```PowerShell
python hello_simple.py
```

### 1.2. More Structured Hello World

This is a more structured version that you'd use in real projects or scripts:

```python
def main():
    print("Hello, World!")

if __name__ == "__main__":
    main()
```

Save this file as `hello.py` and run it with `python hello.py`.  Why write the program this way?  It allows you to import this script as a module into another script.  Without the `if __name__ == "__main__"` guard, the `print("Hello, World!")` line would run even when the file is imported, which is usually not what you want.

> Terminology:
>
> - A _script_ is a `.py` file that's run directly (usually has a `main` as shown above).
> - A _module_ is any `.py` file, whether it is executed directly or imported.
>
> Note that every script is a module, and not every module is a script.

### 1.3. Calling hello.py From Other Module

This shows how one module can import and invoke a function from another.  In this case, the module being called is the `hello.py` script developed in the previous subsection.

```python
import hello

hello.main()
```

Save this as `call_hello.py` in the same directory as `hello.py`, and run it with `python call_hello.py`.

## 2. Statement Organization And Whitespace

### 2.1. Indentation Is Syntax

Python does not use opening and closing braces or keywords like `begin` and `end` to group statements; rather, consistent indentation defines blocks of code.

```python
if True:
    print("This line is inside the block.")
    print("So is this line.")
print("This is outside the block")

```

### 2.2. How Much Indentation?

The standard is 4 spaces per level.

- Do not use tabs.
- Python will raise an error if you mix tabs and spaces in the same file, and even if it doesn't, results may vary between editors or environments.
- The [PEP 8 Style Guide for Python Code](https://peps.python.org/pep-0008/) recommends 4 spaces, and formatters commonly follow this

### 2.3. Colons Start Blocks

Any block-opening statement ends in a colon (`:`), such as:

```python
if condition:
    ...
for x in iterable:
    ...
while something:
    ...
def my_function():
    ...
class MyClass:
    ...
try:
    ...
```

### 2.4. One Statement Per Line (Usually)

You typically write one statement per line.

But if needed you can:

- Use semicolons (`;`) to write multiple statements on one line (allowed but un-Pythonic):

  ```python
  x = 1; y = 2
  ```

- Use backslashes (`\`) for explicit line continuation (rarely needed):

  ```python
  result = some_long_function_name(arg1, arg2, arg3, \
      arg4, arg5)
  ```

  But Python prefers implicit continuation inside:

  - Parentheses `()`
  - Brackets `[]`
  - Braces `{}`

  ```python
  result = some_long_function_name(
      arg1, arg2, arg3,
      arg4, arg5 
  )
  ```

### 2.5. Blank Lines And Grouping

- Blank lines are allowed freely &mdash; they help group logical sections.
- Two blank lines between top-level functions and classes is the convention per [PEP 8](https://peps.python.org/pep-0008/).

### 2.6. Gotchas

- Indentation must be consistent within a block.
- Mixing tabs and spaces may work on your machine and fail elsewhere.
- Accidentally misaligning a line will silently alter logic.  Python won’t warn if the indentation is syntactically valid but semantically wrong.

## 3. Comments

### 3.1. Single-Line Comments

On any line, the Python interpreter ignores from the first `#` character to end of line.

```python
# This is a full-line comment explaining the next line
print("Hello, world!")  # This inline comment is also ignored by Python
```

When an inline comment follows code on the same line, it is suggested to separate the code and the comment by at least two spaces for readability.

### 3.2. Multi-Line Comments

Unlike some languages (C, Java, etc.), Python does not have a special syntax for multi-line block comments​.  Instead, use multiple successive single-line comments, like this:

```python
# This is a multi-line comment constructed by
# prefixing each line with a hash. It can span 
# multiple lines as needed.
```

While this may seem inconvenient for developers accustomed to a block comment syntax, modern integrated development environments (IDEs) typically have a feature to comment or uncomment a block of code.  This works around the problem.

Triple-quoted strings (delimited by either `"""` or `'''`) can be used as multi-line comments.  If a string literal appears by itself (not assigned to a variable or used in an expression), it is usually ignored at runtime.  For example:

```python
"""
This triple-quoted string is not assigned to any variable,
so it acts as a multi-line comment. Python skips it entirely
at runtime.
"""
print("This line will execute")
```

Use the triple-quoted string technique with caution.  A triple-quoted string appearing as the first statement of a function, class, or module is treated as a docstring (documentation string) for the code object rather than as a comment.  When interpreted as a docstring, the triple-quoted string is stored in memory and available for introspection (e.g. via `help()` or `.__doc__`), like this:

```python
def greet(name):
    """Return a friendly greeting for the given name."""
    return f"Hello, {name}!"

# Now access the docstring
print(greet.__doc__)     # prints the docstring
help(greet)
```

(Note: the string `f"Hello, {name}!"` is an example of string interpolation in Python. `f` is short for "formatted string," and it allows you to embed variables or expressions inside `{}`.)

Expected output:

```text
Return a friendly greeting for the given name.
Help on function greet in module __main__:

greet(name)
    Return a friendly greeting for the given name.
```

To avoid uncertainty regarding whether triple-quoted strings are loaded into memory, some developers stick with the `#` syntax for multi-line comments.

### 3.3. Comment Style

The [PEP 8 Style Guide](https://peps.python.org/pep-0008/#comments) has much to say about commenting style.  Check it out and proceed as you see fit.  This guide skips those details, for brevity.

## 4. Naming Conventions

Python follows naming conventions defined in [PEP 8](https://peps.python.org/pep-0008/).  These aren't enforced by the interpreter, but they are widely followed in the Python community.  Stick to these, and your code will feel "Pythonic."

> NOTE: This section needs to touch on many things in Python that are named, so many new language constructs are mentioned.  An effort has been made to include just enough explanation here to keep the material from feeling disorienting at this stage.  Sections beyond this one provide deeper explanations of topics first mentioned here.

### 4.1. Summary Table

| Use                        | Convention        | Example                    |
|----------------------------|-------------------|----------------------------|
| Variables                  | `snake_case`      | `user_id`, `total_count`   |
| Functions and methods      | `snake_case`      | `process_data()`           |
| Classes                    | `PascalCase`      | `DataParser`, `UserAuth`   |
| Constants                  | `ALL_CAPS`        | `MAX_RETRIES`, `PI`        |
| Module (file) names        | `snake_case.py`   | `data_utils.py`            |
| Package (folder) names     | `snake_case/`     | `my_library/`              |
| "Private" members          | `_leading_underscore` | `_internal_helper()`  |
| Name mangling (rare)       | `__double_leading`   | `__internal_data`       |
| Special Python methods     | `__dunder__`       | `__init__`, `__str__`      |

(Name mangling is a way to make certain names harder to accidentally access or override. It's mostly used in class code, which we’ll cover later.)

### 4.2. Variables And Functions

Use lowercase with underscores (`snake_case`) for variable names, function names, and method names.

```python
def calculate_average(values):
    total = sum(values)
    return total / len(values)
```

Avoid `camelCase` and short cryptic names unless truly obvious in context (e.g., i, x, y in a short loop).

### 4.3. Classes

Class names use `PascalCase` (sometimes called `UpperCamelCase`).  Do not use underscores.

```python
class DataProcessor:
    def process(self, data):
        pass
```

(Note: `pass` is Python for "do nothing".)

### 4.4. Constants

Constants are named in `ALL_CAPS`, typically defined at the top of a module.

```python
MAX_ATTEMPTS = 5
PI = 3.14159
```

### 4.5. Underscores and Visibility

Python doesn’t enforce access restrictions (`private`, `protected`, etc.). Instead, it uses naming conventions:

- `_single_leading_underscore`: intended for internal use &mdash; a hint to readers and tools that it’s not part of the public API.
- `__double_leading_underscore`: triggers name mangling &mdash; makes the name harder to access from outside (e.g., from subclasses). Rarely used in practice.
- `__double_underscores__` (“dunder”): reserved for Python-defined special methods like `__init__`, `__str__`, etc. Do not invent your own.

### 4.6. Modules And Packages

- Module names (i.e., `.py` files) should use `snake_case`, all lowercase. Avoid dashes or capital letters.  Examples: `math_utils.py`, `my_script.py`
- Package names (i.e., folders containing modules) follow the same `snake_case` convention.

The presence of a file named `__init__.py` (even if empty) tells Python to treat the directory as a package.

```text
my_package/
├── __init__.py
├── parser.py
├── constants.py
```

### 4.7. Style Guidance

- Avoid names like `l`, `O`, or `I` &mdash; they’re visually ambiguous.
- Choose clear names over short ones &mdash; Python values readability over brevity.
- Let tools like the [black](https://github.com/psf/black) code formatter, the [flake8](https://flake8.pycqa.org/en/latest/) linter, or your IDE guide you.  Tools like this typically apply [PEP 8](https://peps.python.org/pep-0008/) by default.

### 4.8. Summary

Use `snake_case` for most things, `PascalCase` for classes, `ALL_CAPS` for constants. Avoid `camelCase`. Use `_` to signal internal use, and `__dunder__` only for Python’s special methods.

## 5. Control Flow

Python provides standard control flow constructs like `if`, `for`, and `while`, along with a few distinctive features. As with other Python syntax, indentation defines blocks.  There are no braces.

### 5.1. if Statement

```python
if x > 0:
    print("Positive")
elif x == 0:
    print("Zero")
else:
    print("Negative")
```

- Use `elif` instead of `else if`.
- Parentheses around conditions are allowed but not required (and not idiomatic).
- The colon at the end of each control line starts a new block, defined by indentation.

### 5.2. for Loop

Python's `for` loops iterate directly over items in a sequence.

```python
for name in ["Alice", "Bob", "Charlie"]:
    print(name)
```

To iterate over a range of numbers:

```python
for i in range(5):  # 0 through 4
    print(i)
```

To iterate both index and value, use `enumerate()`:

```python
for i, name in enumerate(["Alice", "Bob"]):
    print(i, name)
```

To iterate over two sequences in parallel, use `zip()`:

```python
for name, score in zip(["Alice", "Bob"], [85, 92]):
    print(name, score)
```

### 5.3. while Loop

Python's `while` loops are straightforward:

```python
while x > 0:
    print(x)
    x -= 1
```

As with `for` loops, indentation defines the block. No parentheses are needed around the condition.

### 5.4. break And continue

These work as in other C-like languages:

```python
for ch in "hello":
    if ch == "l":
        continue
    if ch == "o":
        break
    print(ch)
```

- `continue` skips to the next iteration.
- `break` exits the loop.

### 5.5. No switch Or case Statement

Python does not have a `switch` or `case` statement.  Instead, use a chain of `if`/`elif`/`else` statements, or use a dictionary for dispatch, as shown below:

```python
def handle(choice):
    return {
        "start": "Starting...",
        "stop": "Stopping...",
        "pause": "Pausing...",
    }.get(choice, "Unknown command")
```

The code inside `{}` defines what other languages call a map or dictionary (called a dict in Python).  `get(choice, "Unknown command")` tries to do a lookup in the dict, mapping `choice` to the associated value in the dict.  If the key is not found, `"Unknown command"` is returned instead.

Note that dict lookup using square brackets `[]` is also supported; however, that was not used here by design.  `get()` provides a safe lookup, whereas `[]` throws an error if the key is not found.

### 5.6. match Statement

Starting in Python 3.10, there is a new `match` statement, often referred to as _structural pattern matching_.

```python
command = "start"

match command:
    case "start":
        print("Starting")
    case "stop":
        print("Stopping")
    case _:
        print("Unknown command") # Default case
```

It's not quite the same as a `switch` in other languages, because it supports powerful pattern matching, not just value matching.

### 5.7. else With Loops

Python allows an `else` clause on `for` and `while` loops. It runs only if the loop completes normally &mdash; that is, not interrupted by a `break`.

```python
for x in [1, 2, 3]:
    if x == 0:
        break
else:
    print("No zero found")  # This line runs
```

This is an uncommon feature but occasionally useful in search patterns.

### 5.8. Summary

- Use `if` / `elif` / `else` for conditional logic.
- Python’s `for` loops iterate over sequences, not numeric indices.
- Python's `while` is straightforward.
- Use `range()`, `enumerate()`, and `zip()` to control iteration.
- `break` and `continue` work as expected.
- Python has no `switch`; use `if` chains or dicts instead.
- Python does have a `match`, which is a bit like a `switch` and supports powerful pattern matching.
- Loops support an optional `else` clause that runs if not exited by `break`.

("dict" is the Python term for what is known as a dictionary or map in other languages.  Python has a built-in type `dict`.)

## 6. Operators And Precedence

Python supports common arithmetic, comparison, logical, and bitwise operators. Precedence rules are similar to those in C-like languages, though Python encourages the use of parentheses to make expressions readable.

### 6.1. Arithmetic Operators

```python
a + b    # addition
a - b    # subtraction
a * b    # multiplication
a / b    # division (always returns float)
a // b   # integer (floor) division
a % b    # modulus
a ** b   # exponentiation
```

> Note: `/` always returns a float, even if both operands are integers.

### 6.2. Comparison Operators

```python
a == b    # equal
a != b    # not equal
a < b     # less than
a <= b    # less than or equal
a > b     # greater than
a >= b    # greater than or equal
```

Python supports chained comparisons:

```python
if 0 < x < 10:
    ...
```

This is equivalent to `(0 < x) and (x < 10)`, and is idiomatic in Python.

### 6.3. Logical Operators

```python
a and b
a or b
not a
```

Python uses these keywords rather than `&&`, `||`, or `!`. Logical expressions short-circuit as in other C-like languages:

```python
if a is not None and a > 0:
    ...
```

(`None` is a singleton object that represents the absence of a value or a null value.  This is covered in greater depth in the section on [Core Data Structures](#7-core-data-structures).)

### 6.4. Identity Versus Equality

Python distinguishes between **equality** (`==`) and **identity** (`is`):

```python
a == b    # values are equal
a is b    # objects are identical (same memory)
```

Use `is` when comparing to `None`.

```python
if value is None:
    ...
```

In general, use `==` to compare values.

### 6.5. Boolean Values

Python has `True` and `False`, both capitalized. These are of type `bool`, which is a subclass of `int`:

```python
True == 1     # True
False == 0    # True
```

This behavior exists for historical reasons. It’s better to treat booleans as distinct from numbers.

### 6.6. Bitwise Operators

```python
a & b     # bitwise AND
a | b     # bitwise OR
a ^ b     # bitwise XOR
~a        # bitwise NOT
a << n    # left shift
a >> n    # right shift
```

Same syntax and behavior as in C-like languages.

### 6.7. Assignment Expressions

Python 3.8 introduced the **assignment expression operator** `:=`, sometimes called the “walrus operator.” It allows you to assign a value to a variable **as part of an expression**.

```python
if (n := len(data)) > 0:
    print(f"{n} items found.")
```

This is equivalent to:

```python
n = len(data)
if n > 0:
    print(f"{n} items found.")
```

Assignment expressions are useful when:

- You want to **avoid repeating a costly or verbose expression**
- You need to **both capture a value and test it**

> Avoid overusing `:=`. It's best used when it improves clarity, not just to write fewer lines. For simple cases, regular assignment remains more readable.

### 6.8. Operator Precedence

The table below shows a simplified but complete view of operator precedence. Operators higher in the list bind more tightly than those lower down.

| Precedence (high → low)   | Category               | Operators & Examples                            |
|---------------------------|------------------------|--------------------------------------------------|
| 1                         | **Parentheses**        | `( ... )` — grouping, overrides precedence       |
| 2                         | **Exponentiation**     | `**`                                             |
| 3                         | **Unary**              | `+x`, `-x`, `~x`, `not x`                        |
| 4                         | **Multiplicative**     | `*`, `/`, `//`, `%`                              |
| 5                         | **Additive**           | `+`, `-`                                         |
| 6                         | **Bitwise Shifts**     | `<<`, `>>`                                       |
| 7                         | **Bitwise AND**        | `&`                                              |
| 8                         | **Bitwise XOR**        | `^`                                              |
| 9                         | **Bitwise OR**         | `\|`                                              |
| 10                        | **Comparisons, Identity, and Membership** | `<`, `<=`, `>`, `>=`, `==`, `!=`<br>`is`, `is not`<br>`in`, `not in` |
| 11                        | **Boolean `not`**      | `not x`                                          |
| 12                        | **Boolean `and`**      | `x and y`                                        |
| 13                        | **Boolean `or`**       | `x or y`                                         |
| 14                        | **Assignment**         | `=`, `+=`, `-=`, `*=`, `/=`, etc.                |
| 15                        | **Assignment Expression** | `:=` (walrus operator)                      |

---

**Notes:**

- All comparison, identity, and membership operators share the same precedence level but are grouped by purpose for clarity.
- Parentheses always win — use them liberally to clarify intent.
- Logical operators (`not`, `and`, `or`) have relatively low precedence.
- Bitwise and arithmetic operators follow precedence similar to C/C++.
- The **walrus operator `:=`** binds even more loosely than `=`, meaning it’s safe to use in conditionals without surprises.

**Additional note:**

> This table is simplified in the sense that it omits a few rarely used constructs (such as `lambda`, attribute access, function calls, and indexing), as well as technical parsing rules like associativity. It includes all core operators introduced in this guide.  For the complete precedence table, see the [official Python documentation](https://docs.python.org/3/reference/expressions.html#operator-precedence).

### 6.9. Summary

- Arithmetic and comparison operators behave as expected.
- Use `and`, `or`, and `not` — not `&&`, `||`, or `!`.
- Use `==` for value equality, `is` for object identity.
- `True` and `False` are of type `bool`, which is a subclass of `int`.
- Bitwise operators resemble other C-like languages.
- Operator precedence mostly follows C-like rules, but parentheses are preferred for clarity.

## 7. Core Data Structures
