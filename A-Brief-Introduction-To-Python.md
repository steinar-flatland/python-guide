# A Brief Introduction To Python

> _This guide is incomplete.  This message will be removed when a first draft is complete._

<!--BEGIN_TOC-->
- [A Brief Introduction To Python](#a-brief-introduction-to-python)
  - [1. Hello World](#1-hello-world)
    - [1.1. Hello World v1](#11-hello-world-v1)
    - [1.2. Hello World v2](#12-hello-world-v2)
    - [1.3. Hello World v3](#13-hello-world-v3)
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
    - [4.5. Modules And Packages](#45-modules-and-packages)
    - [4.6. Underscores and Visibility](#46-underscores-and-visibility)
    - [4.7. Style Guidance](#47-style-guidance)
    - [4.8. Summary](#48-summary)
  - [5. Control Flow](#5-control-flow)
    - [5.1. if Statement](#51-if-statement)
    - [5.2. for Loop](#52-for-loop)
    - [5.3. while Loop](#53-while-loop)
    - [5.4. break And continue](#54-break-and-continue)
    - [5.5. else With Loops](#55-else-with-loops)
    - [5.6. No switch Or case Statement](#56-no-switch-or-case-statement)
    - [5.7. match Statement](#57-match-statement)
    - [5.8. Exception Handling](#58-exception-handling)
    - [5.9. with Statement](#59-with-statement)
    - [5.10. Summary](#510-summary)
  - [6. Operators And Precedence](#6-operators-and-precedence)
  - [7. General Information About Types](#7-general-information-about-types)
    - [7.1. Dynamic Typing](#71-dynamic-typing)
    - [7.2. Truth Testing](#72-truth-testing)
    - [7.3. Comparison](#73-comparison)
    - [7.4. Mutable And Immutable](#74-mutable-and-immutable)
  - [8. Types](#8-types)
    - [8.1. Numeric Types](#81-numeric-types)
      - [8.1.1. int](#811-int)
      - [8.1.2. float](#812-float)
      - [8.1.3. complex](#813-complex)
    - [8.2. bool](#82-bool)
    - [8.3. General Information About Sequences](#83-general-information-about-sequences)
      - [8.3.1. What Is A Sequence?](#831-what-is-a-sequence)
      - [8.3.2. Common Sequence Operations](#832-common-sequence-operations)
      - [8.3.3. Immutable Sequence Operations](#833-immutable-sequence-operations)
      - [8.3.4. Mutable Sequence Operations](#834-mutable-sequence-operations)
      - [8.3.5. Built-In Sequence Summary](#835-built-in-sequence-summary)
    - [8.4. Basic Sequence Types](#84-basic-sequence-types)
      - [8.4.1. list](#841-list)
      - [8.4.2. tuple](#842-tuple)
      - [8.4.3. range](#843-range)
    - [8.5. str](#85-str)
    - [8.6. Binary Sequence Types](#86-binary-sequence-types)
      - [8.6.1. bytes](#861-bytes)
      - [8.6.2. bytearray](#862-bytearray)
      - [8.6.3. memoryview](#863-memoryview)
    - [8.7. Set Types](#87-set-types)
      - [8.7.1. set](#871-set)
      - [8.7.2. frozenset](#872-frozenset)
    - [8.8. dict](#88-dict)
    - [8.9. Types About Types](#89-types-about-types)
      - [8.9.1. NoneType](#891-nonetype)
        - [8.9.1.1. What Is None?](#8911-what-is-none)
        - [8.9.1.2. Type and Identity](#8912-type-and-identity)
        - [8.9.1.3. Truthiness](#8913-truthiness)
      - [8.9.2. type](#892-type)
        - [8.9.2.1. Uses As Function](#8921-uses-as-function)
        - [8.9.2.2. Used As Class](#8922-used-as-class)
        - [8.9.2.3. Summary](#8923-summary)
  - [9. Other Built-In Types](#9-other-built-in-types)
  - [10. Functions And Parameter Passing](#10-functions-and-parameter-passing)
    - [10.1. Defining A Function](#101-defining-a-function)
    - [10.2. Returning Values](#102-returning-values)
    - [10.3. Default Parameters](#103-default-parameters)
    - [10.4. Positional And Keyword Arguments](#104-positional-and-keyword-arguments)
    - [10.5. Arbitrary Arguments](#105-arbitrary-arguments)
    - [10.6. Parameter Passing Model](#106-parameter-passing-model)
    - [10.7. Summary](#107-summary)
  - [11. Next Topics](#11-next-topics)
<!--END_TOC-->

This is an introduction to Python for experienced programmers who are new to the language.  It offers a curated selection of essential concepts to help you get up to speed quickly.

See also:  Official [Python documentation](https://docs.python.org) and the [Python Tutorial](https://docs.python.org/3/tutorial/index.html).

For clarity and convenience, this guide includes some excerpts from the official Python documentation, used under the terms of the [Python Software Foundation License](https://docs.python.org/3/license.html).  All excerpts include a link back to the original source for attribution and deeper reference.

It is assumed you already have Python installed and available at the shell prompt.

## 1. Hello World

### 1.1. Hello World v1

This is the simplest possible hello world program:

```python
print("Hello, World!")
```

Save this as `hello_simple.py`.  To run it:

```PowerShell
python hello_simple.py
```

All `.py` files are Python _modules_.   A _module_ is just a `.py` file with some Python code in it.

Some Python modules, including the above example, are intended to be the starting point of execution.  When the author of a Python module designs it for passing to the interpreter directly (e.g. `python filename.py`), then the module, more specifically, is a _script_.

Summary of _module_ vs. _script:

- Every `.py` file is a module.
- Not every module is a script.  A script is a `.py` file that the author designs for passing to the `python` interpreter to start program execution.
- `.py` file might be a module but not a script.  Such a module holds code for reuse by other modules through an import mechanism.

### 1.2. Hello World v2

This version of the hello world program has a `main()` function.  It is designed both for running as an independent script and for importing into another module that wants to use the function.

```python
def main():
    print("Hello, World!")

if __name__ == "__main__":
    main()
```

Save this file as `hello.py` and run it with `python hello.py`.

`if __name__ == "__main__:"` is a conditional guard that has the following effect:

- When running `python hello.py`, the interpreter immediately calls `main()`.
- When importing `hello.py` into another module, the interpreter does not call `main()`; rather, the module doing the importing must call `main()` explicitly.

### 1.3. Hello World v3

This example shows how to import the module of the previous section and call its `main()` function:

```python
import hello

hello.main()
```

Save this code as `call_hello.py` in the same directory as `hello.py`, and run it with `python call_hello.py`.

## 2. Statement Organization And Whitespace

### 2.1. Indentation Is Syntax

Python does not use opening and closing braces or keywords like `begin` and `end` to group statements; rather, consistent indentation defines blocks of code.

```python
if True:
    print("This line is inside the block.")
    print("So is this line.")
print("This line is outside the block")

```

### 2.2. How Much Indentation?

The standard is 4 spaces per level.

- Do not use tabs.
- Python raises an error on a mixture of tabs and spaces in the same file, and even if it doesn't, results may vary between editors or environments.
- The [PEP 8 Style Guide for Python Code](https://peps.python.org/pep-0008/) recommends 4 spaces, and formatters commonly follow this.

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

One statement per line is the norm.

Use semicolons (`;`) to write multiple statements on one line (allowed but un-Pythonic):

```python
x = 1; y = 2
```

To continue long lines:

- Use backslashes (`\`) for explicit line continuation (rarely needed):

  ```python
  result = some_long_function_name(arg1, arg2, arg3, \
      arg4, arg5)
  ```

- Python prefers implicit continuation inside:

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

- The interpreter ignores blank lines.
- Use blank lines to separate logical sections of code.
- Two blank lines between top-level functions and classes is the convention per [PEP 8](https://peps.python.org/pep-0008/).

### 2.6. Gotchas

- Indentation must be consistent within a block.
- Mixing tabs and spaces may work in the local development environment and then fail elsewhere.
- Accidentally misaligning a line can silently alter logic.  Python does not warn if the indentation is syntactically valid but semantically incorrect.

## 3. Comments

### 3.1. Single-Line Comments

On any line, the Python interpreter ignores from the first `#` character to end of line.

```python
# This is a full-line comment explaining the next line
print("Hello, world!")  # This inline comment is also ignored by Python
```

When an inline comment follows code on the same line, it is suggested to separate the code and the comment by at least two spaces for readability.

### 3.2. Multi-Line Comments

Unlike some languages, Python does not have a special syntax for multi-line block comments​.  Instead, use multiple successive single-line comments, like this:

```python
# This is a multi-line comment constructed by
# prefixing each line with a hash. It can span 
# multiple lines as needed.
```

While this may seem inconvenient for developers accustomed to a block comment syntax, modern integrated development environments (IDEs) typically have a feature to comment or uncomment a block of code.  This works around the problem.

Triple-quoted strings (delimited by either `"""` or `'''`) can be used as multi-line comments, with some caveats.  If a string literal appears by itself (not assigned to a variable or used in an expression), it is _usually_ ignored at runtime.  For example:

```python
"""
This triple-quoted string is not assigned to any variable,
so it acts as a multi-line comment. Python skips it entirely
at runtime.
"""
print("This line will execute")
```

Use the triple-quoted string commenting technique with caution.  A triple-quoted string appearing as the first statement of a function, class, or module is treated as a docstring (documentation string) for the code object rather than as a comment.  When interpreted as a docstring, the triple-quoted string is stored in memory and available for introspection (e.g. via `help()` or `.__doc__`), like this:

```python
def greet(name):
    """Return a friendly greeting for the given name."""
    return f"Hello, {name}!"

# Now access the docstring
print(greet.__doc__)     # prints the docstring
help(greet)
```

(Note: the string `f"Hello, {name}!"` is an example of string interpolation in Python. `f` is short for "formatted string," and it allows embedding of variables or expressions inside `{}`.)

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

The Python community widely follows naming conventions defined in [PEP 8](https://peps.python.org/pep-0008/).  The Python interpreter does not require the use of these naming conventions, but following them is good practice.  Following the conventions makes code feel "Pythonic".

> This section needs to touch on many things in Python that are named, so many language constructs are mentioned.  An effort has been made to include just enough explanation here to keep the material from feeling disorienting at this stage.  Sections beyond this one provide deeper explanations of topics first mentioned here.

### 4.1. Summary Table

| Construct                        | Convention        | Example                    |
|----------------------------|-------------------|----------------------------|
| Variables                  | `snake_case`      | `user_id`, `total_count`   |
| Functions and methods      | `snake_case`      | `process_data()`           |
| Classes                    | `PascalCase`      | `DataParser`, `UserAuth`   |
| Constants                  | `ALL_CAPS`        | `MAX_RETRIES`, `PI`        |
| Module (file) names        | `snake_case.py`   | `data_utils.py`            |
| Package (folder) names     | `snake_case/`     | `my_library/`              |
| "Private" members          | `_leading_underscore` | `_internal_helper()`  |
| Name mangling       | `__double_leading`   | `__internal_data`       |
| Special Python methods     | `__dunder__`       | `__init__`, `__str__`      |

### 4.2. Variables And Functions

Use lowercase with underscores (`snake_case`) for variable names, function names, and method names.

```python
def calculate_average(values):
    total = sum(values)
    return total / len(values)
```

Avoid `camelCase` and short cryptic names unless truly obvious in context (e.g., `i`, `x`, `y` in a short loop).

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

### 4.5. Modules And Packages

- Module names (i.e., `.py` files) should use `snake_case`, all lowercase. Avoid dashes or capital letters.  Examples: `math_utils.py`, `my_script.py`.
- Package names (i.e., folders containing modules) follow the same `snake_case` convention.

The presence of a file named `__init__.py` (even if empty) tells Python to treat the directory as a package.

```text
my_package/
├── __init__.py
├── parser.py
├── constants.py
```

### 4.6. Underscores and Visibility

Python doesn’t enforce access restrictions (`private`, `protected`, etc.). Instead, it uses naming conventions:

- `_single_leading_underscore`: intended for internal use &mdash; a hint to readers and tools that it’s not part of the public API.
- `__double_leading_underscore`: triggers name mangling, which makes the name harder to access from outside (e.g., from subclasses).  More on this later, in a discussion on object oriented programming.
- `__double_underscores__` (“dunder”): reserved for Python-defined special methods like `__init__`, `__str__`, etc. Do not invent your own.

### 4.7. Style Guidance

- Avoid names like `l`, `O`, or `I` because they are visually ambiguous.
- Choose clear names over short ones.  Python values readability over brevity.
- Let tools like the [black](https://github.com/psf/black) code formatter, the [flake8](https://flake8.pycqa.org/en/latest/) linter, or your IDE guide you.  Tools like this typically apply [PEP 8](https://peps.python.org/pep-0008/) by default.

### 4.8. Summary

Use `snake_case` for most things, `PascalCase` for classes, and `ALL_CAPS` for constants. Avoid `camelCase`. Use `_` to signal internal use, and `__dunder__` only for Python’s special methods.

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

### 5.5. else With Loops

Python allows an `else` clause on `for` and `while` loops. It runs only if the loop completes normally &mdash; that is, not interrupted by a `break`.

```python
for x in [1, 2, 3]:
    if x == 0:
        break
else:
    print("No zero found")  # This line runs
```

This is an uncommon feature but occasionally useful in search patterns.

### 5.6. No switch Or case Statement

Python does not have a `switch` or `case` statement.  Instead, use a chain of `if`/`elif`/`else` statements, or use a dictionary for dispatch, as shown below:

```python
def handle(choice):
    return {
        "start": "Starting...",
        "stop": "Stopping...",
        "pause": "Pausing...",
    }.get(choice, "Unknown command")
```

The code inside `{}` defines what other languages call a map or dictionary (called a dict in Python).  Python has a built-in type `dict`.  `get(choice, "Unknown command")` tries to do a lookup in the `dict`, mapping `choice` to the associated value in the `dict`.  If the key is not found, `"Unknown command"` is returned instead.

Note that `dict` lookup using square brackets `[]` is also supported; however, that was not used here by design.  `get()` provides a safe lookup, whereas `[]` throws an error if the key is not found.

### 5.7. match Statement

Starting in Python 3.10, there is a new `match` statement, often referred to as [_structural pattern matching_](https://peps.python.org/pep-0636/).

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

### 5.8. Exception Handling

Python has a familiar feeling exception handling feature.

```python
def divide(a, b):
    try:
        result = a / b
        print(f"Result: {result}")
    except ZeroDivisionError:
        print("Error: Cannot divide by zero.")
    finally:
        print("Cleaning up...")

divide(10, 2)   # Successful division
divide(10, 0)   # Triggers exception
```

- The `try` block contains code that might fail.
- An `except` block handles an error gracefully.
- A `finally` block, if provided, always runs.  This is useful for cleanup, logging, closing resources, etc.

Multiple `except` blocks are allowed.  If multiple `except` blocks:

- At most one `except` block (first match) runs.
- If none match, the exception is unhandled and propagates.
- Catching multiple exception types in one block is allowed:

```python
except (ValueError, TypeError):
    print("Caught either a ValueError or TypeError.")
```

### 5.9. with Statement

`with` statements ensure that resources like files will be released when the program is done with them.  For example:

```python
# Open and read a file using the with statement
try:
    with open("example.txt", "r") as file:
        contents = file.read()
        print(contents)
except FileNotFoundError:
    print("The file was not found.")
```

- Calling `file.close()` is not necessary.  The `with` takes care of that.
- Even if `file.read()` raises an exception, the file is closed.

### 5.10. Summary

- Use `if` / `elif` / `else` for conditional logic.
- Python’s `for` loops iterate over sequences, not numeric indices.
- Python's `while` is straightforward.
- Use `range()`, `enumerate()`, and `zip()` to control iteration.
- `break` and `continue` work as expected.
- Loops support an optional `else` clause that runs if not exited by `break`.
- Python has no `switch`; use `if` chains or `dict` instead.
- Python does have a `match`, which is a bit like a `switch` and supports powerful pattern matching.
- Use `try` / `except` / `finally` for exception handling.
- Use `with` to help avoid resource leakage.

For more information, see Python's article on [Compound Statements](https://docs.python.org/3/reference/compound_stmts.html).

## 6. Operators And Precedence

Python has a rich set of operators.  They are covered in the [Expressions](https://docs.python.org/3/reference/expressions.html#) section of Python's documentation.

For reference, this is Python's operator precedence table, based on the full table from the [Operator precedence](https://docs.python.org/3/reference/expressions.html#operator-precedence) section of the official documentation.  The official table has additional details and footnotes.

| Operator | Description |
|----------|-------------|
| `(expressions...)`, `[expressions...]`, `{key: value...}`, `{expressions...}` | Binding or parenthesized expression, list display, dictionary display, set display |
| `x[index]`, `x[index:index]`, `x(arguments...)`, `x.attribute` | Subscription, slicing, call, attribute reference |
| `await x` | Await expression |
| `**` | Exponentiation |
| `+x`, `-x`, `~x` | Positive, negative, bitwise NOT |
| `*`, `@`, `/`, `//`, `%` | Multiplication, matrix multiplication, division, floor division, remainder |
| `+`, `-` | Addition and subtraction |
| `<<`, `>>` | Shifts |
| `&` | Bitwise AND |
| `^` | Bitwise XOR |
| `\|` | Bitwise OR |
| `in`, `not in`, `is`, `is not`, `<`, `<=`, `>`, `>=`, `!=`, `==` | Comparisons, including membership tests and identity tests |
| `not` | Boolean NOT |
| `and` | Boolean AND |
| `or` | Boolean OR |
| `x if y else z` | Conditional expression (ternary operator) |
| `lambda` | Lambda expression |
| `:=` | Assignment expression |

Even with many Python-specific features, this table still feels familiar to developers who are coming from C-like languages.

## 7. General Information About Types

This section covers general information about Python's type system.

### 7.1. Dynamic Typing

The first and most important thing to understand about Python and types is that the language is dynamically typed. This means:

- Type checking occurs at runtime.
- There is no need to declare variable types.
- While flexible, dynamic typing is generally considered less safe than static typing.

Here's a short program that illustrates dynamic typing:

```python
x = 42
print(type(x))   # <class 'int'>

x = "forty-two"
print(type(x))   # <class 'str'>
```

The type of a variable can change at any time during execution.  This is because a variable is just a name bound to an object, not a container with a fixed type.

- Every object has a permanent, unchangeable type.
- A variable can be rebound to a different object at any time.
- A variable's current "type" is really just the type of the object it refers to right now.

### 7.2. Truth Testing

Any object, regardless of its type, can be tested for truth in an `if` statement, `while` loop, or using Boolean operators such as `==`, `<`, `>`, and so on.

The following built-in objects are considered falsy (i.e., they evaluate to `False` in a Boolean context):

- The built-in constant `None`, which refers to a singleton object representing the absence of a value (similar to `null` in Java or C#)
- The Boolean constant `False`
- Empty sequences and collections

The table below shows common falsy expressions involving empty sequences and collections:

| Expression | Type | Meaning |
|------------|------|---------|
| `''`, `""` | `str` | Empty string |
| `()` | `tuple` | Empty tuple |
| `[]` | `list` | Empty list |
| `{}` | `dict` | Empty dictionary (not a set!) |
| `set()` | `set` | Empty set |
| `range(0)` | `range` | An empty range (a sequence of 0 values) |

More detail on the types listed above is provided in the next section on [Types](#8-types).

To describe how object values behave in Boolean contexts, the Python community uses the terms _truthy_ and _falsy_.  A falsy value is one that evaluates to `False`. Everything else is truthy.

One final note: When using Python for object-oriented programming, instances of user-defined classes are truthy by default.  To customize this behavior, a class can define the method `__bool__(self)` to control its truth value.

### 7.3. Comparison

There are 8 comparison operators in Python.  Each compares two objects and produces a Boolean result.  The operators are:

`<`, `<=`, `>`, `>=`, `==`, `!=`, `is`, `is not`

Here are some key points to help you use them effectively:

- `==` and `!=` can be applied to any pair of objects. Except for numeric types, objects of different types generally do not compare equal.
- Numbers of different types (e.g., `int` vs. `float`) can be compared using all six relational operators.  
- `<`, `<=`, `>`, `>=` raise a `TypeError` when used between types that cannot be meaningfully ordered (e.g., comparing an `int` to a `str`)
- `is` tests whether two objects are _identical_ (i.e., the same object in memory).
- `is not` is the logical negation of `is`.

Ordering comparisons (`<`, `<=`, `>`, `>=`) are defined on some built-in types but not others. For example:

- `list` and `tuple` support lexicographic comparison
- `set` supports subset/superset comparisons using these operators
- `dict` does not support ordering comparisons at all

A full discussion of type-specific behavior appears in the next section: [Types](#8-types).

Proceed with caution.  This is an area that can surprise even experienced developers new to Python.

### 7.4. Mutable And Immutable

All types in Python are either _mutable_ or _immutable_.  Mutable types can be changed after they are created.  Immutable types cannot.  Mutability is important, because it affects how data behaves when passed around, stored, or shared.

The following built-in types are **mutable**:

| Type         | Description                                     | Example                    |
|--------------|-------------------------------------------------|----------------------------|
| `list`       | Ordered, mutable sequence                       | `[1, 2, 3]`                |
| `dict`       | Mutable key-value mapping                       | `{"a": 1, "b": 2}`         |
| `set`        | Unordered, mutable collection of unique values  | `{1, 2, 3}`                |
| `bytearray`  | Mutable sequence of bytes                       | `bytearray(b"hello")`      |

The following built-in types are **immutable**:

| Type                | Description                            | Example                      |
|---------------------|----------------------------------------|------------------------------|
| `int`              | Integer numbers                         | `42`                         |
| `float`            | Floating-point numbers                  | `3.14`                       |
| `complex`          | Complex numbers                         | `2 + 3j`                     |
| `bool`             | Boolean values                          | `True`, `False`              |
| `str`              | Text (Unicode string)                   | `"hello"`                    |
| `tuple`            | Ordered, immutable sequence             | `(1, 2, 3)`                  |
| `frozenset`        | Immutable set                           | `frozenset([1, 2, 3])`       |
| `bytes`            | Immutable sequence of bytes             | `b"hello"`                   |
| `range`            | Immutable sequence of integers          | `range(10)`                  |
| `NoneType`         | Singleton null value                    | `None`                       |
| `type`             | Type objects (types themselves)         | `type(42)`, `type(str)`      |

The `memoryview` type can be either mutable or immutable, depending upon how it was instantiated.

> 💡 **Mutability Of User-Defined Classes**:  Most user-defined classes in Python are _mutable_ by default.  Unless you explicitly design your class to prevent modification, its instances can typically have attributes added, removed, or updated.  To enforce immutability, you can override `__setattr__`, use `__slots__`, or apply a decorator like `@dataclass(frozen=True)` from the `dataclasses` module.

This section references numerous Python built-in types.  For more details, see the next section on [Types](#8-types).

## 8. Types

This section introduces many of Python's built-in types.

Familiarity with the preceding section, [General Information About Types](#7-general-information-about-types), is assumed.

See also: Python's official documentation on [Built-in Types](https://docs.python.org/3/library/stdtypes.html).

### 8.1. Numeric Types

Python has three built-in numeric types:

- integers (`int`)
- floating point (`float`)
- complex (`complex`)

(Python's standard library has additional numeric types [`fractions.Fraction`](https://docs.python.org/3/library/fractions.html#module-fractions) for rational numbers and [`decimal.Decimal`](https://docs.python.org/3/library/decimal.html#decimal-objects) for floating-point numbers where the user can define the precision.)

Arithmetic using operands of different types is supported, yielding a result of the wider type.

With the exception of complex numbers, comparison between numbers of different types is supported.

Numeric types (except complex) support the following operations.  For more details, see Python's article on [Numeric Types](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex).

| Operation                         | Result                               |
|----------------------------------|---------------------------------------|
| `x + y`                          | sum of `x` and `y`                    |
| `x - y`                          | difference of `x` and `y`             |
| `x * y`                          | product of `x` and `y`                |
| `x / y`                          | quotient of `x` and `y`               |
| `x // y`                         | floored quotient of `x` and `y`       |
| `x % y`                          | remainder of `x` / `y`                |
| `-x`                             | `x` negated                           |
| `+x`                             | `x` unchanged                         |
| `abs(x)`                         | absolute value or magnitude of `x`    |
| `int(x)`                         | `x` converted to integer              |
| `float(x)`                       | `x` converted to floating point       |
| `complex(re, im)`                | a complex number with real part `re`, imaginary part `im`.`im`.  Defaults to `0.` |
| `c.conjugate()`                  | conjugate of the complex number `c`   |
| `divmod(x, y)`                   | the pair `(x // y, x % y)`            |
| `pow(x, y)` or `x ** y`          | `x` raised to the power `y`           |

See also the [math](https://docs.python.org/3/library/math.html#module-math) module for additional mathematical functions that apply to numeric types that extend from `numbers.Real` (`int`, `float`, [`fractions.Fraction`](https://docs.python.org/3/library/fractions.html#module-fractions), [`decimal.Decimal`](https://docs.python.org/3/library/decimal.html#decimal-objects)).

See also the [cmath](https://docs.python.org/3/library/cmath.html#module-cmath) module for additional mathematical functions for complex numbers.

#### 8.1.1. int

Languages such as C, Java, and C#, which have fixed width integer types that wrap around or overflow.  In contrast, the Python `int` type has unlimited precision, limited only by the memory of the machine where the program is running.

In addition to the numeric functions already discussed, `int` supports the following [bitwise operations](https://docs.python.org/3/library/stdtypes.html#bitwise-operations-on-integer-types):

| Operation        | Result                              |
|------------------|-------------------------------------|
| `x \| y`         | bitwise or of `x` and `y`           |
| `x ^ y`          | bitwise exclusive or of `x` and `y` |
| `x & y`          | bitwise and of `x` and `y`          |
| `x << n`         | `x` shifted left by `n` bits        |
| `x >> n`         | `x` shifted right by `n` bits       |
| `~x`             | the bits of `x` inverted            |

`int` also supports the following [additional functions](https://docs.python.org/3/library/stdtypes.html#additional-methods-on-integer-types):

- `int.bit_length()`
- `int.bit_count()`
- `int.to_bytes(length=1, byteorder='big', *, signed=False)`
- `classmethod int.from_bytes(bytes, byteorder='big', *, signed=False)`
- `int.as_integer_ratio()`
- `int.is_integer()`

See also the [math](https://docs.python.org/3/library/math.html#module-math) module for additional mathematical functions that apply to `int`.

Sample code creating `ints` and using `int` functions:

```python
# Define integers
a = 13         # binary: 1101
b = 4          # binary: 0100

print(f"a = {a} (binary: {a:04b})")                      # a = 13 (binary: 1101)
print(f"b = {b} (binary: {b:04b})\n")                    # b = 4 (binary: 0100)

# Truth testing
print(f"bool({a}) = {bool(a)}")                          # bool(13) = True
print(f"bool(0) = {bool(0)}")                            # bool(0) = False
if a:
    print(f"{a} is truthy")                              # 13 is truthy
if not 0:
    print("0 is falsy")                                  # 0 is falsy
print("\n")

# Comparison operators
print(f"a < b = {a < b}")                                # a < b = False
print(f"a <= b = {a <= b}")                              # a <= b = False
print(f"a > b = {a > b}")                                # a > b = True
print(f"a >= b = {a >= b}")                              # a >= b = True
print(f"a == b = {a == b}")                              # a == b = False
print(f"a != b = {a != b}\n")                            # a != b = True

# Arithmetic operations
print(f"a + b = {a + b}")                                # a + b = 17
print(f"a - b = {a - b}")                                # a - b = 9
print(f"a * b = {a * b}")                                # a * b = 52
print(f"a / b = {a / b}")                                # a / b = 3.25
print(f"a // b = {a // b}")                              # a // b = 3
print(f"a % b = {a % b}")                                # a % b = 1
print(f"a ** b = {a ** b}\n")                            # a ** b = 28561

# Unary minus and absolute value
print(f"-a = {-a}")                                      # -a = -13
print(f"abs(-a) = {abs(-a)}\n")                          # abs(-a) = 13

# divmod returns a tuple: (quotient, remainder)
print(f"divmod(a, b) = {divmod(a, b)}\n")                # divmod(a, b) = (3, 1)

# Bitwise operations
print(f"a << 1 = {a << 1} (binary: {(a << 1):05b})")     # a << 1 = 26 (binary: 11010)
print(f"a >> 1 = {a >> 1} (binary: {(a >> 1):04b})")     # a >> 1 = 6 (binary: 0110)
print(f"a & b = {a & b} (binary: {(a & b):04b})")        # a & b = 4 (binary: 0100)
print(f"a | b = {a | b} (binary: {(a | b):04b})")        # a | b = 13 (binary: 1101)
print(f"a ^ b = {a ^ b} (binary: {(a ^ b):04b})")        # a ^ b = 9 (binary: 1001)
print(f"~a = {~a} (bitwise NOT of {a})\n")               # ~a = -14 (bitwise NOT of 13)

# Bit introspection
print(f"a.bit_length() = {a.bit_length()}")              # a.bit_length() = 4
print(f"a.bit_count() = {a.bit_count()}\n")              # a.bit_count() = 3

# Integer to bytes and back
x = 1025
x_bytes = x.to_bytes(2, byteorder='big')
print(f"{x} to bytes (2 bytes, big-endian): {x_bytes}")  # 1025 to bytes (2 bytes, big-endian): b'\x04\x01'
for i, byte in enumerate(x_bytes):
    print(f"  byte {i}: {byte} (binary: {byte:08b})")    #   byte 0: 4 (binary: 00000100)
                                                         #   byte 1: 1 (binary: 00000001)
print(f"Bytes {x_bytes} back to int: {int.from_bytes(x_bytes, 'big')}\n")  # Bytes b'\x04\x01' back to int: 1025

# Float methods
f = 0.75
print(f"{f} as integer ratio: {f.as_integer_ratio()[0]}/{f.as_integer_ratio()[1]}")  # 0.75 as integer ratio: 3/4
g = 5.0
h = 5.1
print(f"{g} is_integer? {g.is_integer()}")               # 5.0 is_integer? True
print(f"{h} is_integer? {h.is_integer()}\n")             # 5.1 is_integer? False
```

#### 8.1.2. float

The Python `float` type is typically implemented as a C `double` &mdash; a 64-bit representation based on the [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754) standard.

Floating-point arithmetic is subject to precision limitations due to binary representation. Operations may produce small rounding errors (as in most languages that follow IEEE 754).

In addition to the numeric functions already discussed, `float` supports the following [additional functions](https://docs.python.org/3/library/stdtypes.html#additional-methods-on-float):

- `float.as_integer_ratio()`
- `float.is_integer()`
- `float.hex()`
- `classmethod float.fromhex(s)`

See also the [math](https://docs.python.org/3/library/math.html#module-math) module for additional mathematical functions that apply to `float`.

Sample code creating `floats` and using `float` functions:

```python
# Define floats
a = 5.75
b = 2.5

print(f"a = {a}")                                # a = 5.75
print(f"b = {b}\n")                              # b = 2.5

# Truth testing
print(f"bool({a}) = {bool(a)}")                  # bool(5.75) = True
print(f"bool(0.0) = {bool(0.0)}")                # bool(0.0) = False
if a:
    print(f"{a} is truthy")                      # 5.75 is truthy
if not 0.0:
    print("0.0 is falsy")                        # 0.0 is falsy
print("\n")

# Comparison operators
print(f"a < b = {a < b}")                        # a < b = False
print(f"a <= b = {a <= b}")                      # a <= b = False
print(f"a > b = {a > b}")                        # a > b = True
print(f"a >= b = {a >= b}")                      # a >= b = True
print(f"a == b = {a == b}")                      # a == b = False
print(f"a != b = {a != b}\n")                    # a != b = True

# Arithmetic operations
print(f"a + b = {a + b}")                        # a + b = 8.25
print(f"a - b = {a - b}")                        # a - b = 3.25
print(f"a * b = {a * b}")                        # a * b = 14.375
print(f"a / b = {a / b}")                        # a / b = 2.3
print(f"a // b = {a // b}")                      # a // b = 2.0
print(f"a % b = {a % b}")                        # a % b = 0.75
print(f"-a = {-a}")                              # -a = -5.75
print(f"abs(-a) = {abs(-a)}")                    # abs(-a) = 5.75
print(f"divmod(a, b) = {divmod(a, b)}")          # divmod(a, b) = (2.0, 0.75)
print(f"pow(a, b) = {pow(a, b)}\n")              # pow(a, b) = 79.28108986976339

# Float-specific methods
print(f"a.as_integer_ratio() = {a.as_integer_ratio()[0]}/{a.as_integer_ratio()[1]}")  # a.as_integer_ratio() = 23/4
print(f"a.is_integer() = {a.is_integer()}")      # a.is_integer() = False
print(f"b.is_integer() = {b.is_integer()}\n")    # b.is_integer() = False

# Hex representation and conversion
print(f"a.hex() = {a.hex()}")                    # a.hex() = 0x1.7000000000000p+2
# 0x1.7000000000000p+2 means:
#   0x1.7  → 1 + 7/16 = 1.4375
#   p+2    → multiply by 2^2 = 4
# Result: 1.4375 × 4 = 5.75
print(f"float.fromhex(a.hex()) = {float.fromhex(a.hex())}\n")  # float.fromhex(a.hex()) = 5.75
```

#### 8.1.3. complex

Python implements complex numbers through the `complex` type.  Complex numbers consist of a real part and an imaginary part, each represented by a floating point number.  In Python code, an expression like `2 + 3j` represents a complex number, where `2` is the real part, and `3j` is the imaginary part. `j` represents the imaginary unit (√–1), following the convention used in electrical engineering (where `i` is typically used for current).

If the imaginary part is `0`, the value behaves like a float in most respects.  For example, `3 + 0j` is of type `complex` but acts like `3.0` in calculations.

Extract the real and imaginary parts using `z.real` and `z.imag`.

See also the [cmath](https://docs.python.org/3/library/cmath.html#module-cmath) module for additional mathematical functions for complex numbers.

Example of using complex numbers:

```python
# Define two complex numbers
z1 = 2 + 3j
z2 = 1 - 4j

# Arithmetic operations
print(f"z1 = {z1}")                  # z1 = (2+3j)
print(f"z2 = {z2}")                  # z2 = (1-4j)
print(f"z1 + z2 = {z1 + z2}")        # z1 + z2 = (3-1j)
print(f"z1 * z2 = {z1 * z2}")        # z1 * z2 = (14-5j)
print(f"z1 / z2 = {z1 / z2}")        # z1 / z2 = (-0.5882352941176471+0.6470588235294118j)

# Access real and imaginary parts
print(f"Real part of z1: {z1.real}")        # 2.0
print(f"Imaginary part of z1: {z1.imag}")   # 3.0

# Built-in complex() function
z3 = complex(0, -1)
print(f"z3 = {z3}")                  # z3 = -1j

# Example: solving a quadratic equation with a negative discriminant
# Solving: x² + 2x + 5 = 0
# Discriminant is negative → complex roots
# Formula: (-b ± sqrt(b² - 4ac)) / (2a)
import cmath
a, b, c = 1, 2, 5
discriminant = cmath.sqrt(b**2 - 4*a*c)
root1 = (-b + discriminant) / (2*a)
root2 = (-b - discriminant) / (2*a)
print(f"Roots of x² + 2x + 5 = 0 are {root1} and {root2}")
# Roots are complex: (-1+2j) and (-1-2j)
```

### 8.2. bool

The Boolean type in Python is `bool`.  There are two constant instances of this type:  `True` and `False`.

The built-in function `bool()` converts any value or expression to `bool` according to whether it is truthy or falsy as discussed earlier in the [Truth Testing](#72-truth-testing) section.

Use the operators `and`, `or`, and `not` to build logical expressions.  Like in many languages, `and` and `or` are short-circuiting: Evaluation stops as soon as the result is determined.

Note that when each of the bitwise operators `&`, `|`, `^` is  applied to a pair of booleans, the result is a `bool` equivalent to applying the logical operations "and", "or", and "xor", respectively.

`bool` is a subclass of `int`, where `False` is like `0` and `True` is like `1`.  Good Python style discourages relying on this, however.  Passing a `bool` value to the `int()` function to convert to `int` explicitly is encouraged.

```python
# 1. True and False are instances of bool
print(type(True))    # <class 'bool'>
print(type(False))   # <class 'bool'>

# 2. Using bool() to test truthiness
print(bool(0))       # False
print(bool(42))      # True
print(bool(""))      # False
print(bool("hello")) # True

# 3. Logical operators: and, or, not
a = True
b = False
print(a and b)       # False
print(a or b)        # True
print(not a)         # False

# 4. Bitwise operators on booleans (act like logical ops)
print(True & False)  # False (like True and False)
print(True | False)  # True  (like True or False)
print(True ^ False)  # True  (exclusive or)

# 5. bool is a subclass of int
print(int(True))     # 1
print(int(False))    # 0
print(True + True)   # 2 (discouraged style — shown for demonstration only)
```

### 8.3. General Information About Sequences

#### 8.3.1. What Is A Sequence?

In Python, a _sequence_ is an ordered collection of items accessible by integer indices.

All built-in sequences share these key properties:

- **Ordered**: The items have a defined order, and this order is preserved.
- **Indexed**: Items can be accessed using zero-based integer indexing.
- **Sliceable**: Portions of the sequence can be extracted using slice notation (`seq[start:stop:step]`).
- **Iterable**: Sequences can be looped over using `for` loops and comprehensions.
- **Length-aware**: The `len()` function returns the number of items in the sequence.

Some sequences are **mutable** (e.g., `list`, `bytearray`), meaning their contents can be changed after creation. Others are **immutable** (e.g., `tuple`, `str`, `range`, `bytes`), meaning they cannot be changed in place.

Python defines sequence behavior formally through abstract base classes in the [`collections.abc`](https://docs.python.org/3/library/collections.abc.html) module:

- `collections.abc.Sequence`: defines the interface for **immutable sequences**
- `collections.abc.MutableSequence`: extends `Sequence` with mutation methods (e.g., `append`, `remove`)

Most of Python’s built-in sequence types conform to one of these interfaces. These base classes aren’t typically used directly, but they define expected behavior and can be used for `isinstance()` checks in more advanced code.

> 💡 **Note on `isinstance()`**  
>
> Python provides a built-in function `isinstance(obj, type)` to check whether an object is an instance of a particular class or abstract base class.  
>
> For example, to check if something behaves like a sequence:
>
> ```python
> from collections.abc import Sequence
> 
> items = [1, 2, 3]
> if isinstance(items, Sequence):
>     print("This object supports sequence behavior.")
> ```
>
> This works not just for built-in types like `list` or `tuple`, but for any object that conforms to the expected interface.

#### 8.3.2. Common Sequence Operations

For reference, the table below shows common operations supported by most sequences, whether mutable or immutable.  The table is based on the section, [Common Sequence Operations](https://docs.python.org/3/library/stdtypes.html#common-sequence-operations), from the official Python documentation.  Please see the official table for important footnotes.

According to the official documentation:

> This table lists the sequence operations sorted in ascending priority. In the table, `s` and `t` are sequences of the same type, `n`, `i`, `j` and `k` are integers and `x` is an arbitrary object that meets any type and value restrictions imposed by `s`.

| Operation              | Result                                                                    |
|------------------------|---------------------------------------------------------------------------|
| `x in s`               | `True` if an item of `s` is equal to `x`, else `False`                    |
| `x not in s`           | `False` if an item of `s` is equal to `x`, else `True`                    |
| `s + t`                | the concatenation of `s` and `t`                                          |
| `s * n` or `n * s`     | equivalent to adding `s` to itself `n` times                              |
| `s[i]`                 | `i`th item of `s`, origin 0                                               |
| `s[i:j]`               | slice of `s` from `i` to `j`                                              |
| `s[i:j:k]`             | slice of `s` from `i` to `j` with step `k`                                |
| `len(s)`               | length of `s`                                                             |
| `min(s)`               | smallest item of `s`                                                      |
| `max(s)`               | largest item of `s`                                                       |
| `s.index(x[, i[, j]])` | index of the first occurrence of `x` in `s` (at or after `i`, before `j`) |
| `s.count(x)`           | total number of occurrences of `x` in `s`                                 |

#### 8.3.3. Immutable Sequence Operations

The only functionality implemented by immutable sequences that is not implemented by mutable sequences, is support for [`hash()`](https://docs.python.org/3/library/functions.html#hash).  `hash()` returns the hash value of an object.

Since immutable sequences support `hash()`, they may be used as `dict` keys and stored in `set` and `frozenset` instances.

Mutable sequences do not implement the `hash()` method because their contents can be changed after creation. Hash values must remain constant for the lifetime of an object, as they are used to determine the object's position in hash tables.

#### 8.3.4. Mutable Sequence Operations

For reference, the table below shows the operations defined on mutable sequences.  The table is based on the section, [Mutable Sequence Types](https://docs.python.org/3/library/stdtypes.html#mutable-sequence-types), from the official Python documentation.  Please see the official table for important footnotes.

According to the official documentation:

> In the table `s` is an instance of a mutable sequence type, `t` is any iterable object and `x` is an arbitrary object that meets any type and value restrictions imposed by `s` (for example, `bytearray` only accepts integers that meet the value restriction `0 <= x <= 255`).

| Operation                 | Result                                                                       |
|---------------------------|------------------------------------------------------------------------------|
| `s[i] = x`                | item `i` of `s` is replaced by `x`                                           |
| `s[i:j] = t`              | slice of `s` from `i` to `j` is replaced by the contents of the iterable `t` |
| `del s[i:j]`              | same as `s[i:j] = []`                                                        |
| `s[i:j:k] = t`            | the elements of `s[i:j:k]` are replaced by those of `t`                      |
| `del s[i:j:k]`            | removes the elements of `s[i:j:k]` from the list                             |
| `s.append(x)`             | appends `x` to the end of the sequence                                       |
| `s.clear()`               | removes all items from `s`                                                   |
| `s.copy()`                | creates a shallow copy of `s`                                                |
| `s.extend(t)` or `s += t` | extends `s` with the contents of `t`                                         |
| `s *= n`                  | updates `s` with its contents repeated `n` times                             |
| `s.insert(i, x)`          | inserts `x` into `s` at the index given by `i`                               |
| `s.pop()` or `s.pop(i)`   | retrieves the item at `i` and also removes it from `s`                       |
| `s.remove(x)`             | removes the first item from `s` where `s[i]` is equal to `x`                 |
| `s.reverse()`             | reverses the items of `s` in place                                           |

#### 8.3.5. Built-In Sequence Summary

This table summarizes the built-in sequence types, their mutability, and notes about how they are used.

| Type       | Mutability | Notes                             |
|------------|------------|-----------------------------------|
| `list`     | Mutable    | General-purpose                   |
| `tuple`    | Immutable  | Often used for fixed-size records |
| `str`      | Immutable  | Text                              |
| `range`    | Immutable  | Lightweight numeric sequence      |
| `bytes`    | Immutable  | Binary data                       |
| `bytearray`| Mutable    | Mutable binary data               |

### 8.4. Basic Sequence Types

The three basic sequence types are `list`, `tuple`, and `range`.

#### 8.4.1. list

The `list` type is Python’s most commonly used built-in sequence. It is ordered, mutable, and heterogeneous &mdash; it can contain elements of different types.

Lists are defined using square brackets:

```python
fruits = ["apple", "banana", "cherry"]
```

Common list operations:

```python
fruits = ["apple", "banana", "cherry"]

print(fruits[0])                 # apple — indexing
print(fruits[-1])                # cherry — negative indexing
print(fruits[1:])                # ['banana', 'cherry'] — from index 1 to end

fruits.append("date")            # Add to end
print(fruits)                    # ['apple', 'banana', 'cherry', 'date']

fruits[1] = "blueberry"          # Mutate by assignment
print(fruits)                    # ['apple', 'blueberry', 'cherry', 'date']

fruits[0:2] = ["kiwi", "mango"]  # Mutate by slice assignment
print(fruits)                    # ['kiwi', 'mango', 'cherry', 'date']

del fruits[2]                    # Remove by index
print(fruits)                    # ['kiwi', 'mango', 'date']

fruits.remove("kiwi")            # Remove by value
print(fruits)                    # ['mango', 'date']

print(len(fruits))               # 2 — list length
```

Iteration and membership:

```python
for fruit in fruits:
    print(fruit)

if "date" in fruits:
    print("Yes, we have dates.")
```

Lists are not restricted to a single data type:

```python
mixed = [1, "two", 3.0, [4, 5], {"six": 6}]
print(mixed[3])        # [4, 5] — a nested list
```

List comprehensions provide a concise way to create new lists:

```python
squares = [x * x for x in range(5)]
print(squares)         # [0, 1, 4, 9, 16]
```

You can add conditions in a list comprehension:

```python
evens = [x for x in range(10) if x % 2 == 0]
print(evens)           # [0, 2, 4, 6, 8]
```

> 💡 For large lists or complex transformations, list comprehensions often replace manual loops.

Assigning a list to a new variable creates a reference, not a copy:

```python
a = [1, 2, 3]
b = a
b.append(4)
print(a)               # [1, 2, 3, 4] — same object as `b`
```

To copy:

```python
b = a.copy()           # or: b = list(a) or b = a[:]
```

Note that `copy()` produces a shallow copy:

```python
nested = [[1], [2]]
copy = nested.copy()
copy[0][0] = 99
print(nested)           # [[99], [2]] — inner lists are shared
```

Example of a deep copy:

```python
import copy
nested = [[1], [2]]
copy = copy.deepcopy(nested)
copy[0][0] = 99
print(nested)  # [[1], [2]]   # original unaltered
print(copy)    # [[99], [2]]  # deep copy was modified
```

#### 8.4.2. tuple

The `tuple` type is an immutable sequence. Tuples are often used to group related values together, especially when their structure is fixed.

Tuples are defined using parentheses:

```python
point = (3, 4)
```

You can also omit the parentheses when defining a tuple:

```python
color = "red", 255, 0
print(color)  # ('red', 255, 0)
```

A single-element tuple requires a trailing comma:

```python
singleton = (42,)
print(type(singleton))  # <class 'tuple'>
```

Indexing and slicing work like with lists:

```python
numbers = (10, 20, 30, 40)

print(numbers[1])     # 20
print(numbers[-1])    # 40
print(numbers[1:3])   # (20, 30)
```

Tuples support iteration and membership testing:

```python
for n in numbers:
    print(n)

if 30 in numbers:
    print("Found 30")
```

Tuples can contain any types, including other tuples or lists:

```python
mixed = (1, "two", [3, 4], (5, 6))
print(mixed[2])  # [3, 4]
```

Although tuples are immutable, if they contain mutable elements, those elements can still be modified:

```python
t = ([1, 2], 3)
t[0].append(99)
print(t)  # ([1, 2, 99], 3)
```

Tuples are commonly used to return multiple values from functions:

```python
def divide(x, y):
    return x // y, x % y

quotient, remainder = divide(7, 3)
print(quotient, remainder)  # 2 1
```

You can unpack tuples directly:

```python
name, age, city = ("Alice", 30, "NYC")
print(city)  # NYC
```

> 💡 **Tip:** Use tuples when the structure of the data is fixed, and you want to prevent accidental modification.

#### 8.4.3. range

The `range` type represents an immutable sequence of integers. It's most commonly used for looping a specific number of times or generating integer sequences efficiently.

A `range` object doesn't store all numbers in memory. Instead, it computes items on demand, making it memory-efficient even for large ranges.

```python
r = range(5)
print(r)               # range(0, 5)
print(list(r))         # [0, 1, 2, 3, 4]
```

You can create ranges with one, two, or three arguments:

```python
print(list(range(5)))           # [0, 1, 2, 3, 4]
print(list(range(2, 6)))        # [2, 3, 4, 5]
print(list(range(2, 10, 2)))    # [2, 4, 6, 8]
print(list(range(10, 2, -2)))   # [10, 8, 6, 4]
```

Ranges support indexing, slicing, membership tests, and iteration:

```python
r = range(10)
print(r[2])           # 2 — indexing
print(r[-1])          # 9 — negative indexing
print(r[2:5])         # range(2, 5) — slicing returns another range
print(5 in r)         # True — membership test

for i in r:
    print(i, end=" ")  # 0 1 2 3 4 5 6 7 8 9 — iteration
print()
```

Ranges are useful for indexing and enumeration:

```python
names = ["Alice", "Bob", "Charlie"]
for i in range(len(names)):
    print(i, names[i])
```

Or more Pythonically, use `enumerate()`:

```python
for i, name in enumerate(names):
    print(i, name)
```

> 💡 `range` objects behave like read-only sequences. You can index, slice, and iterate over them, but you can't change them in place.

### 8.5. str

The `str` type represents a sequence of Unicode characters. Strings are immutable.

Strings are created using single or double quotes:

```python
s1 = "hello"
s2 = 'world'
```

Multi-line strings can use triple quotes:

```python
s3 = """This is
a multiline
string."""
```

Strings support indexing, slicing, and iteration:

```python
text = "Python"

print(text[0])     # P — first character
print(text[-1])    # n — last character
print(text[1:4])   # yth — slice from index 1 up to (but not including) 4

for ch in text:
    print(ch)
```

Strings are immutable:

```python
# text[0] = "J"     # TypeError: 'str' object does not support item assignment
```

Concatenation and repetition:

```python
greeting = "Hi, "
name = "Alice"
print(greeting + name)     # "Hi, Alice"
print("ha" * 3)            # "hahaha"
```

Membership testing:

```python
print("py" in "python")    # True
print("z" not in "python") # True
```

Length:

```python
print(len("hello"))        # 5
```

Strings support a large number of [methods](https://docs.python.org/3/library/stdtypes.html#string-methods). A few examples:

```python
s = "  hello, world!  "

print(s.strip())                     # "hello, world!" — remove surrounding whitespace
print(s.upper())                     # "  HELLO, WORLD!  "
print(s.replace("world", "Python"))  # "  hello, Python!  "
print(s.startswith("  he"))          # True
print(s.endswith("!  "))             # True
```

Splitting and joining:

```python
csv = "red,green,blue"
colors = csv.split(",")
print(colors)                       # ['red', 'green', 'blue']

joined = "-".join(colors)
print(joined)                       # "red-green-blue"
```

Formatted strings:

```python
name = "Bob"
age = 30
print(f"{name} is {age} years old.")  # "Bob is 30 years old."
```

Strings can also be encoded into bytes:

```python
s = "café"
b = s.encode("utf-8")
print(b)           # b'caf\xc3\xa9'
```

To decode bytes back into a string:

```python
decoded = b.decode("utf-8")
print(decoded)     # "café"
```

> 💡 When reading and writing files or handling network data, encoding and decoding strings is important.

To view all available string methods:

```python
help(str)
```

### 8.6. Binary Sequence Types

As stated in the official Python documentation for [Binary Sequence Types](https://docs.python.org/3/library/stdtypes.html#binary-sequence-types-bytes-bytearray-memoryview):

> The core built-in types for manipulating binary data are `bytes` and `bytearray`. They are supported by `memoryview` which uses the [buffer protocol](https://docs.python.org/3/c-api/buffer.html) to access the memory of other binary objects without needing to make a copy.

These types represent sequences of bytes &mdash; integers in the range 0–255 &mdash; and are used for working with raw binary data such as file contents, network packets, or low-level protocol buffers. While `bytes` is immutable and behaves similarly to a `str`, `bytearray` is mutable. `memoryview` provides a zero-copy way to work with buffers exposed by other binary-compatible objects.

#### 8.6.1. bytes

The `bytes` type represents an immutable sequence of bytes (integers in the range 0–255). It is commonly used for handling raw binary data, such as file contents or network messages.

You can define a `bytes` object using a `b` prefix before a string literal:

```python
b = b"hello"
print(b)             # b'hello'
```

Each byte is represented by an integer (0–255). You can index and slice `bytes` just like other sequences:

```python
print(b[0])          # 104 — ASCII code for 'h'
print(b[1:4])        # b'ell'
```

You can also iterate over `bytes` to get individual byte values:

```python
for byte in b:
    print(byte, end=" ")  # 104 101 108 108 111
print()
```

To construct a `bytes` object from a list of integers:

```python
data = bytes([72, 101, 108, 108, 111])
print(data)          # b'Hello'
```

The `bytes` type supports many of the same methods as `str`, especially ones useful for binary-safe processing:

```python
print(b.upper())              # b'HELLO'
print(b.find(b"ell"))         # 1
print(b.replace(b"l", b"x"))  # b'hexxo'
```

Since `bytes` is immutable, any operation that modifies its contents produces a new `bytes` object.

Example of encoding and decoding between `str` and `bytes`:

```python
s = "hello"
encoded = s.encode("utf-8")        # to bytes
decoded = encoded.decode("utf-8")  # back to string
print(encoded)                     # b'hello'
print(decoded)                     # 'hello'
```

Use `bytes` when working with binary files, protocols, or external data that is not inherently textual.

#### 8.6.2. bytearray

The `bytearray` type represents a mutable sequence of bytes (integers in the range 0–255). It behaves similarly to `bytes`, but allows in-place modification of its contents.

To create a `bytearray`:

```python
ba = bytearray([65, 66, 67])
print(ba)               # bytearray(b'ABC')
```

You can also convert a `bytes` object to `bytearray`:

```python
b = b"hello"
ba = bytearray(b)
print(ba)               # bytearray(b'hello')
```

Like other sequences, `bytearray` supports indexing, slicing, and iteration:

```python
print(ba[1])            # 101 — ASCII for 'e'
ba[1] = 120             # Replace 'e' with 'x' (ASCII 120)
print(ba)               # bytearray(b'hxllo')
print(ba[1:4])          # bytearray(b'xll')
```

Appending and extending:

```python
ba.append(33)           # Add '!' (ASCII 33) to the end
print(ba)               # bytearray(b'hxllo!')
ba.extend([32, 87])     # Add space and 'W'
print(ba)               # bytearray(b'hxllo! W')
```

Remove or insert:

```python
del ba[0]               # Remove first byte
print(ba)               # bytearray(b'xllo! W')
ba.insert(0, 72)        # Insert 'H' (ASCII 72) at index 0
print(ba)               # bytearray(b'Hxllo! W')
```

Convert back to `bytes` if needed:

```python
b2 = bytes(ba)
print(b2)               # b'Hxllo! W'
```

`bytearray` is commonly used for working with mutable binary data, especially when performance is important or you need to modify the contents in place.

#### 8.6.3. memoryview

The `memoryview` type provides a way to access the memory of another binary object without copying it. This is especially useful for efficient slicing, manipulation, and I/O operations on large binary data.

You can create a `memoryview` from any object that supports the [buffer protocol](https://docs.python.org/3/c-api/buffer.html), such as `bytes`, `bytearray`, and `array.array`.

```python
data = bytearray(b"hello")
view = memoryview(data)
```

A `memoryview` behaves like a sequence of bytes:

```python
print(view[0])           # 104 — ASCII for 'h'
print(view[1:4])         # <memory at 0x...>
print(bytes(view[1:4]))  # b'ell'
```

Mutating the `memoryview` mutates the underlying object (if it's mutable):

```python
view[0] = 72             # Replace 'h' (104) with 'H' (72)
print(data)              # bytearray(b'Hello')
```

You can use slicing and assignment just like a mutable sequence:

```python
view[1:3] = b"EY"
print(data)              # bytearray(b'HEYlo')
```

You can also create multi-dimensional `memoryviews` from structured data like arrays (e.g., from `array.array`, [NumPy arrays](https://numpy.org/doc/stable/reference/generated/numpy.array.html), or binary files). These use `.cast()` to reshape the view:

```python
import array

# Create an array of unsigned short integers (2 bytes each)
a = array.array("H", [1000, 2000, 3000])  

# Create a memoryview of the array (interprets values as unsigned shorts)
m = memoryview(a)
print(m.tolist())        # [1000, 2000, 3000] — each item is a 2-byte integer

# Cast the memoryview to bytes (reinterpret each element as a single byte)
m_cast = m.cast("B")     # create a new memoryview backed by same array a
print(type(m_cast))      # <class 'memoryview'>
print(m_cast.tolist())   # [232, 3, 208, 7, 184, 11] — raw bytes in little-endian order
```

> 🔒**Mutability Depends On The Source**: A `memoryview` created from a mutable object like `bytearray` or `array.array` allows modifications to the underlying data.  A `memoryview` created from an immutable object like `bytes` or `string` will be read-only, and attempts to modify it will raise a `TypeError`.

Attempting to mutate a `memoryview` that is backed by immutable data causes a `TypeError`:

```python
m = memoryview(b"hello")   # from immutable bytes
print(m.readonly)          # True
m[0] = 72                  # TypeError: cannot modify read-only memory
```

> 💡 Use `memoryview` when performance matters, especially for large data structures or low-level binary manipulations.

### 8.7. Set Types

Sets are useful when you need to eliminate duplicates, perform membership tests, or do mathematical set operations like union and intersection.

There are two built-in set types:  `set` (mutable) and `frozenset` (immutable).

#### 8.7.1. set

The `set` type represents a mutable, unordered collection of unique elements.

You can create a set using curly braces `{}` or the `set()` constructor:

```python
primes = {2, 3, 5, 7}
print(primes)         # {2, 3, 5, 7}

evens = set([2, 4, 6, 8])
print(evens)          # {8, 2, 4, 6} — order is not preserved
```

Sets automatically eliminate duplicates:

```python
nums = {1, 2, 2, 3, 3, 3}
print(nums)           # {1, 2, 3}
```

Membership testing is fast:

```python
if 5 in primes:
    print("5 is prime")
```

Sets are mutable.  You can add or remove elements:

```python
primes.add(11)
primes.remove(3)
print(primes)         # {2, 5, 7, 11}
```

Use `discard()` if you want to remove an item without raising an error if it’s missing:

```python
primes.discard(100)   # OK even if 100 isn't in the set
```

Set operations:

```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a | b)   # {1, 2, 3, 4, 5} — union
print(a & b)   # {3}             — intersection
print(a - b)   # {1, 2}          — difference
print(a ^ b)   # {1, 2, 4, 5}    — symmetric difference (analogous to xor)
```

Other useful methods:

```python
print(len(a))          # 3
print(2 in a)          # True
a.clear()              # Removes all elements
print(a)               # set()
```

> 💡 Sets do not preserve insertion order (in versions before Python 3.7), and they cannot contain mutable or unhashable elements like lists or other sets.

Attempting to include a list in a set results in a `TypeError`:

```python
# set_with_list = {1, [2, 3]}  # TypeError: unhashable type: 'list'
```

> 🔒 The elements of a set must be _hashable_, which means they must be immutable and implement a `__hash__()` method.

#### 8.7.2. frozenset

A `frozenset` is an immutable version of a `set`. Like the `set` type, `frozenset` contains only unique, unordered, hashable elements, but once created, its contents cannot be changed.

You can create a `frozenset` using the built-in constructor:

```python
fs = frozenset([1, 2, 3, 2])
print(fs)             # frozenset({1, 2, 3})
```

sSince `frozenset` is immutable, it does not support methods like `.add()`, `.remove()`, or item assignment. Attempting to mutate it raises an error:

```python
# fs.add(4)           # AttributeError: 'frozenset' object has no attribute 'add'
```

But you can perform all read-only set operations:

```python
a = frozenset([1, 2, 3])
b = frozenset([3, 4, 5])

print(a | b)    # frozenset({1, 2, 3, 4, 5}) — union
print(a & b)    # frozenset({3})             — intersection
print(a - b)    # frozenset({1, 2})          — difference
print(a ^ b)    # frozenset({1, 2, 4, 5})    — symmetric difference (analogous to xor)
```

Since `frozenset` is immutable, it is also hashable and can be used as a key in a `dict`, or as an element in another `set`:

```python
d = {frozenset([1, 2]): "pair"}
print(d[frozenset([1, 2])])  # "pair"
```

> 🔒 Use `frozenset` when you need a set that can safely be used in hashed collections or shared across code without being modified.

### 8.8. dict

A `dict` (short for _dictionary_) is a mutable, unordered collection of key-value pairs. Dictionaries are sometimes called _maps_ or _hash maps_ in other languages. They allow fast lookup, insertion, and deletion of values based on keys.

Dictionaries are one of Python’s most important and flexible data structures. They're commonly used to represent structured data, configuration, caches, symbol tables, frequency counts, and much more.

Dictionaries can be defined using curly braces `{}` with `key: value` pairs, or with the `dict()` constructor:

```python
person = {"name": "Alice", "age": 30, "city": "New York"}
print(person["name"])           # Alice

empty = dict()
print(empty)                    # {}
```

Use square brackets or the `.get()` method to access values by key:

```python
print(person["city"])           # New York
print(person.get("age"))        # 30
#print(person["country"])       # KeyError: 'country'
print(person.get("country"))    # None (no error)

# Demonstrates common pattern of conditional logic
# depending upon whether key was found.
if country := person.get("country"):
    # do something with found value
    print(country)              # None
else:
    # react to value not found
    print(None)
```

You can insert or update values by assignment:

```python
person["email"] = "alice@example.com"
person["age"] = 31
print(person)   # {'name': 'Alice', 'age': 31,
                #  'city': 'New York', 'email': 'alice@example.com'}
```

Dictionaries support multiple ways to remove entries:

```python
del person["city"]
print (person)               # {'name': 'Alice', 'age': 31,
                             #  'email': 'alice@example.com'}
email = person.pop("email")  # removes and returns the value
print (person)               # {'name': 'Alice', 'age': 31}
person.clear()               # removes all items
print (person)               # {}
```

Dictionaries are iterable. You can iterate over keys, values, or key-value pairs:

```python
person = {"name": "Alice", "age": 30}

for key in person:
    print(key)  # name
                # age

for value in person.values():
    print(value)  # Alice
                  # 30

for key, value in person.items():
    print(f"{key} = {value}")  # name = Alice
                               # age = 30
```

> 💡 Starting in Python 3.7, dictionaries preserve insertion order.

Like list comprehensions, dictionary comprehensions provide a concise way to build dictionaries:

```python
squares = {x: x * x for x in range(5)}
print(squares)       # {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

Dictionary keys must be _hashable_, i.e., immutable and uniquely identifiable. Most immutable built-in types (like `int`, `str`, `tuple`, and `frozenset`) are hashable. Mutable types like `list`, `dict`, and `set` are not allowed as keys.

```python
valid = {"a": 1, 10: "ten", (1, 2): "tuple"}
# invalid = {[1, 2]: "oops"}  # TypeError: unhashable type: 'list'
```

Other useful methods include:

- `dict.keys()` — returns a view of keys
- `dict.values()` — returns a view of values
- `dict.items()` — returns a view of key-value pairs
- `dict.update(other)` — merges another dictionary or key-value pairs into this one
- `dict.pop(key[, default])` — removes and returns a value (or default if key not found)
- `key in dict` — tests for key membership

For more methods, refer to [Mapping Types](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict) in the official Python documentation.

> 💡 Dictionaries have excellent performance characteristics for most typical use cases.

### 8.9. Types About Types

#### 8.9.1. NoneType

Python has a special singleton object called `None`, which is the sole instance of the built-in `NoneType`.

##### 8.9.1.1. What Is None?

`None` represents the absence of a value, a placeholder for “nothing” or “no result.” It is often used:

- As a default return value of functions that don’t explicitly return anything
- As a sentinel value to indicate “no input” or “not yet set”
- To signify an optional or missing argument
- In comparisons to check whether a variable or field has been initialized

```python
def greet(name=None):
    if name is None:
        print("Hello, guest!")
    else:
        print(f"Hello, {name}!")

greet()          # Hello, guest!
greet("Alice")   # Hello, Alice!
```

##### 8.9.1.2. Type and Identity

```python
print(type(None))         # <class 'NoneType'>
print(None == None)       # True
print(None is None)       # True
```

You should compare to `None` using `is`, not `==`, because it is a singleton:

```python
if value is None:         # idiomatic
    ...
```

##### 8.9.1.3. Truthiness

`None` is **falsy**, so it evaluates to `False` in boolean contexts:

```python
if not None:
    print("This runs!")   # This runs!
```

#### 8.9.2. type

Python’s built-in `type` object is both a function and a class.

##### 8.9.2.1. Uses As Function

When called with a single argument, `type()` returns the type of the object:

```python
print(type(42))         # <class 'int'>
print(type("hi"))       # <class 'str'>
print(type([1, 2, 3]))  # <class 'list'>
```

This is commonly used for _introspection_ &mdash; checking the type of a value at runtime.

> 💡 Unlike `isinstance()`, `type(obj) == T` only returns `True` if the object is an instance of exactly type `T`, not a subclass of `T`.

Use `isinstance(obj, T)` for more flexible type checks:

```python
print(isinstance(True, int))   # True — bool is a subclass of int
print(type(True) == int)       # False — type is 'bool', not exactly 'int'
```

##### 8.9.2.2. Used As Class

When called with three arguments, `type()` is a _dynamic class constructor_ &mdash; it creates a new type (i.e., class) dynamically at runtime.

```python
# Define a class dynamically
MyClass = type("MyClass", (), {"x": 42})
obj = MyClass()
print(obj.x)          # 42
```

This is rarely needed in beginner-level code but is powerful for advanced use cases like metaprogramming, code generation, and custom class construction in frameworks.

##### 8.9.2.3. Summary

- `type(obj)` &mdash; returns the type of an object (commonly used)
- `type(name, bases, dict)` &mdash; creates a new type dynamically (advanced)

For more details, see the [`type()` built-in function](https://docs.python.org/3/library/functions.html#type).

## 9. Other Built-In Types

To keep this guide focused, certain built-in types are out of scope. Python's full article on [Built-in Types](https://docs.python.org/3/library/stdtypes.html) covers many additional topics, including:

- Generators and iterators  
- Context managers (used with the `with` statement to manage resources)
- Type annotations for better static analysis and editor support
- Introspective types: modules, classes, functions, and methods
- Code objects (representing Python code as data)
- Internal objects like stack frames and traceback objects
- Special singleton values like:
  - `Ellipsis` (`...`)
  - `NotImplemented`
- And more

> This guide focused on the core built-in types you'll encounter in day-to-day Python programming. If you're curious to dig deeper, the [Built-in Types](https://docs.python.org/3/library/stdtypes.html) section of the Python docs is an excellent next step.

## 10. Functions And Parameter Passing

Functions in Python are defined using the `def` keyword. They support default arguments, keyword arguments, and flexible parameter unpacking.

### 10.1. Defining A Function

```python
def greet(name):
    print(f"Hello, {name}!")
```

- Functions use the `def` keyword and a colon to start a block.
- Indentation defines the function body.
- Functions return `None` by default if no `return` is given.

### 10.2. Returning Values

Use `return` to return a value:

```python
def square(x):
    return x * x
```

### 10.3. Default Parameters

You can provide default values:

```python
def greet(name, greeting="Hello"):
    print(f"{greeting}, {name}!")
```

Default arguments are evaluated once when the function is defined, not each time it is called.

>⚠️ **Be careful with mutable defaults** (e.g., lists or dicts):
>
>```python
>def bad(x=[]):
>    x.append(1)
>    return x
>
>print(bad())  # [1]
>print(bad())  # [1, 1] — surprise!
>```
>
>Why this happens:  The default list is created once at definition time.  Each call to `bad()`
>that does not pass in arguments modifies this same list.
>
>Instead, use `None` and assign inside the function:
>
>```python
>def good(x=None):
>    if x is None:
>        x = []
>    x.append(1)
>    return x
>```

### 10.4. Positional And Keyword Arguments

This example refers back to the `greet` function of the previous section.  Arguments can be passed by position or keyword:

```python
greet("Alice", "Hi")                # positional
greet(name="Alice", greeting="Hi")  # keyword
greet(greeting="Hi", name="Alice")  # keyword order is flexible
```

- You may mix the two, but positional arguments must come first.
- Once you use a keyword argument, all remaining arguments must also be keywords.
- Keyword arguments may appear in any order.

### 10.5. Arbitrary Arguments

You can use `*args` and `**kwargs` to accept flexible arguments:

```python
def demo(*args, **kwargs):
    print("Positional:", args)
    print("Keyword:", kwargs)

demo(1, 2, 3, a=10, b=20)
```

- `*args` is a tuple of extra positional args
- `**kwargs` is a dict of extra keyword args

### 10.6. Parameter Passing Model

Python uses _pass-by-assignment_ (a.k.a. “pass-by-object-reference”):

- Arguments are passed as references to objects.
- For mutable objects, changes inside the function can affect the original.
- For immutable objects, reassignment inside the function does not affect the original.

```python
def mutate(lst):
    lst.append(4)

nums = [1, 2, 3]
mutate(nums)
print(nums)  # [1, 2, 3, 4]
```

```python
def reassign(x):
    x = 42

a = 10
reassign(a)
print(a)  # 10 — unchanged
```

In Python, mutability is a property of the type.  Each built-in type is either mutable or immutable by design.  This cannot be controlled on a per-variable basis.  The section [Mutable And Immutable](#74-mutable-and-immutable) categorizes the built-in types as mutable or immutable.

### 10.7. Summary

- Use `def` to define functions; they return `None` by default.
- Use `return` to return a value.
- Use default parameters with care.  Avoid mutable defaults.
- Arguments can be passed by position or keyword.
- Use `*args` and `**kwargs` for flexible parameters.
- Python passes arguments by object reference; mutability determines if changes affect the caller.  Mutability is a property of the type.

## 11. Next Topics

The next topics that will be described in this guide:

- [ ] Program Structure And Scope
- [ ] Exceptions And Error Handling (in more depth)
- [ ] Logging
- [ ] Testing And Assertions
- [ ] Context Manager
- [ ] Working With Files
- [ ] Type Annotations And Optional Static Typing
- [ ] Documentation And Docstrings
- [ ] Comprehensions
- [ ] Classes And Object-Oriented Programming
- [ ] Iterators And Generators
- [ ] Decorators
- [ ] Virtual Environments And Packaging
- [ ] Strings In Depth
- [ ] Data Classes And Named Tuples
- [ ] Type Annotations And Optional Static Typing
- [ ] Argparse
- [ ] Timeit And Profiling
- [ ] Itertools And Functional Tools
- [ ] Concurrency
- [ ] Corutines And asyncio
- [ ] Standard Library Tour / Highlights
- [ ] Metaclasses And Advanced OOP
- [ ] Descriptors And The Data Model
