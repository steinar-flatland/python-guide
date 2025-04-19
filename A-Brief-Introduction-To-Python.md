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
    - [8.3. Basic Sequence Types](#83-basic-sequence-types)
      - [8.3.1. list](#831-list)
      - [8.3.2. tuple](#832-tuple)
      - [8.3.3. range](#833-range)
    - [8.4. str](#84-str)
    - [8.5. Binary Sequence Types](#85-binary-sequence-types)
      - [8.5.1. bytes](#851-bytes)
      - [8.5.2. bytearray](#852-bytearray)
      - [8.5.3. memoryview](#853-memoryview)
    - [8.6. Set Types](#86-set-types)
      - [8.6.1. set](#861-set)
      - [8.6.2. frozenset](#862-frozenset)
    - [8.7. dict](#87-dict)
    - [8.8. Types About Types](#88-types-about-types)
      - [8.8.1. NoneType](#881-nonetype)
      - [8.8.2. type](#882-type)
  - [9. Other Built-In Types](#9-other-built-in-types)
  - [10. Summary](#10-summary)
    - [10.1. String And Binary Types](#101-string-and-binary-types)
      - [10.1.1. String Type](#1011-string-type)
      - [10.1.2. Binary Types](#1012-binary-types)
    - [10.2. Sequence Types](#102-sequence-types)
      - [10.2.1. List (mutable)](#1021-list-mutable)
      - [10.2.2. Tuple (immutable)](#1022-tuple-immutable)
      - [10.2.3. range](#1023-range)
    - [10.3. Set Types](#103-set-types)
      - [10.3.1. set (mutable)](#1031-set-mutable)
      - [10.3.2. frozenset (immutable)](#1032-frozenset-immutable)
    - [10.4. Mapping Types](#104-mapping-types)
      - [10.4.1. dict](#1041-dict)
    - [10.5. Special Types](#105-special-types)
      - [10.5.1. `NoneType` (`None`)](#1051-`nonetype`-`none`)
      - [10.5.2. `type` and `object`](#1052-`type`-and-`object`)
    - [10.6. Summary](#106-summary)
  - [11. Core Data Structures](#11-core-data-structures)
    - [11.1. Lists](#111-lists)
    - [11.2. Tuples](#112-tuples)
    - [11.3. Sets](#113-sets)
    - [11.4. Dictionaries](#114-dictionaries)
    - [11.5. None](#115-none)
    - [11.6. Summary](#116-summary)
  - [12. Functions And Parameter Passing](#12-functions-and-parameter-passing)
    - [12.1. Defining A Function](#121-defining-a-function)
    - [12.2. Returning Values](#122-returning-values)
    - [12.3. Default Parameters](#123-default-parameters)
    - [12.4. Positional And Keyword Arguments](#124-positional-and-keyword-arguments)
    - [12.5. Arbitrary Arguments](#125-arbitrary-arguments)
    - [12.6. Parameter Passing Model](#126-parameter-passing-model)
    - [12.7. Summary](#127-summary)
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

> NOTE: This section needs to touch on many things in Python that are named, so many language constructs are mentioned.  An effort has been made to include just enough explanation here to keep the material from feeling disorienting at this stage.  Sections beyond this one provide deeper explanations of topics first mentioned here.

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

> **Note:** Most user-defined classes in Python are _mutable_ by default.  Unless you explicitly design your class to prevent modification, its instances can typically have attributes added, removed, or updated.  To enforce immutability, you can override `__setattr__`, use `__slots__`, or apply a decorator like `@dataclass(frozen=True)` from the `dataclasses` module.

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

### 8.3. Basic Sequence Types

#### 8.3.1. list

#### 8.3.2. tuple

#### 8.3.3. range

### 8.4. str

### 8.5. Binary Sequence Types

#### 8.5.1. bytes

#### 8.5.2. bytearray

#### 8.5.3. memoryview

### 8.6. Set Types

#### 8.6.1. set

#### 8.6.2. frozenset

### 8.7. dict

### 8.8. Types About Types

#### 8.8.1. NoneType

#### 8.8.2. type

## 9. Other Built-In Types

To keep this guide brief and focused, certain built-in types are out of scope. Python's full article on [Built-in Types](https://docs.python.org/3/library/stdtypes.html) covers many additional topics, including:

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

---------------------------------
---------------------------------
---------------------------------


### 10.1. String And Binary Types

#### 10.1.1. String Type

See also Python's documentation for the [`str` type, also known as Text Sequence Type](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str).

Python has one string type, `str`, for storing an immutable sequence of Unicode characters.

To create a string:

```python
s = "hello"
```

`str` is immutable, and it supports indexing, slicing, and iteration.

```python
s = "Python"
print(s[0])     # "P"     — indexing
print(s[-1])    # "n"     — negative indexing
print(s[1:4])   # "yth"   — slicing from index 1 up to (but not including) 4
print(s[:3])    # "Pyt"   — slice from start to index 3
print(s[3:])    # "hon"   — slice from index 3 to end

# iteration
for char in s:
    print(char)  # Each iteration yields a single-character string
```

Here are a few examples of calling a built-in function on a string:

```python
s = "hello"
print(s.upper())          # "HELLO"
print(s.capitalize())     # "Hello"
print(s.endswith("llo"))  # True
```

For more, see Python's [String Methods](https://docs.python.org/3/library/stdtypes.html#string-methods).  Some other interesting things to do with strings are shown below.

Membership testing:

```python
"py" in "python"  # True
```

Concatenation:

```python
"py" + "thon"  # "python"
```

Repetition:

```python
"ha" * 3  # "hahaha"
```

Formatting:

```python
greeting = "Hello"
name = "Bob"
punctuation = "!"
print(f"{greeting} {name}{punctuation}")  # "Hello Bob!"
```

And so on.

#### 10.1.2. Binary Types

See also Python's documentation for [Binary Sequence Types](https://docs.python.org/3/library/stdtypes.html#binary-sequence-types-bytes-bytearray-memoryview).

Python has two main types for working with binary data: `bytes` and `bytearray`.  Both represent sequences of bytes, but differ in mutability:

- `bytes` is immutable.
- `bytearray` is mutable.

Note that `bytes` literals are prefixed with `b`, like `b"hello"`.

```python
b = b"hello"            # bytes (immutable)
ba = bytearray(b)       # bytearray (mutable)
```

To create an empty instance:

```python
empty_bytes = bytes()
empty_bytearray = bytearray()
```

You can also create them from lists of integers:

```python
raw = bytes([72, 101, 108, 108, 111])  # b'Hello'
```

You can index into either type:

```python
print(b[1])     # 101 — the ASCII code for 'e'
print(ba[1])    # 101
```

With `bytearray`, you can modify contents:

```python
ba[0] = 72      # replace 'h' (104) with 'H' (72)
print(ba)       # bytearray(b'Hello')
```

Like strings, both `bytes` and `bytearray` support slicing and iteration:

```python
for b in b"abc":
    print(b)  # prints 97, 98, 99 (ASCII codes)
print(b"abcdef"[1:4])  # b"bcd"
```

Tip: Iterating over binary types yields integers (byte values 0-255) not characters.

Binary types are useful when:

- Reading or writing binary files
- Processing network packets or byte-oriented protocols
- Performing low-level manipulations or encodings (e.g., UTF-8, Base64)

### 10.2. Sequence Types

Python has several sequence types: `list`, `tuple`, `range`, `str`, and `bytes`.

#### 10.2.1. List (mutable)

See also Python's documentation for ...

Lists are ordered, mutable sequences.

```python
fruits = ["apple", "banana", "cherry"]
```

- Indexable: `fruits[0] == "apple"`
- Mutable: `fruits[1] = "blueberry"`
- Append: `fruits.append("date")`
- Remove: `fruits.remove("banana")`
- Length: `len(fruits)`
- Lists can contain any type, including other lists.

#### 10.2.2. Tuple (immutable)

Tuples are ordered, immutable sequences.

```python
point = (3, 4)
```

- Indexable: `point[0] == 3`
- Immutable: cannot reassign `point[1]`
- Often used for fixed-length groupings
- Parentheses are optional in many contexts: `x, y = 1, 2` defines a tuple
- Single-element tuples require a trailing comma:
  ```python
  one = (42,)      # tuple
  not_a_tuple = (42)  # just an int
  ```

#### 10.2.3. range

Used for iteration over a sequence of numbers.

```python
for i in range(5):
    print(i)  # 0 through 4
```

Efficient: doesn’t store the full sequence in memory.

---

### 10.3. Set Types

Sets are unordered collections of unique elements.

#### 10.3.1. set (mutable)

```python
nums = {1, 2, 3}
nums.add(4)
nums.remove(2)
```

- No duplicates: `{1, 2, 2}` becomes `{1, 2}`
- Unordered: no index access
- Membership: `3 in nums`
- Set operations: union (`|`), intersection (`&`), difference (`-`)

To create an empty set, use `set()`. `{}` creates an empty `dict`.

#### 10.3.2. frozenset (immutable)

```python
f = frozenset([1, 2, 3])
```

Same behavior as `set`, but immutable.

---

### 10.4. Mapping Types

#### 10.4.1. dict

Dictionaries store key-value pairs.

```python
scores = {"Alice": 90, "Bob": 85}
scores["Charlie"] = 88
```

- Keys must be hashable (e.g., strings, numbers, tuples)
- Values can be anything
- Access: `scores["Alice"]`
- Add/update: `scores["Dave"] = 95`
- Remove: `del scores["Bob"]`
- Safe lookup: `scores.get("Eve", 0)`
- Iteration:
  ```python
  for name, score in scores.items():
      print(name, score)
  ```

---

### 10.5. Special Types

#### 10.5.1. `NoneType` (`None`)

Represents the absence of a value.

```python
x = None
if x is None:
    ...
```

#### 10.5.2. `type` and `object`

- `type(x)` returns the type of `x`
- `object` is the base class of all types

---

### 10.6. Summary

| Category       | Types                            |
|----------------|----------------------------------|
| Numeric        | `int`, `float`, `complex`, `bool` |
| Text/Binary    | `str`, `bytes`, `bytearray`      |
| Sequence       | `list`, `tuple`, `range`, `str`  |
| Set            | `set`, `frozenset`               |
| Mapping        | `dict`                           |
| Special        | `None`, `type`, `object`         |

- Some types are **mutable** (`list`, `dict`, `set`, `bytearray`)
- Others are **immutable** (`int`, `float`, `str`, `tuple`, `bytes`, `frozenset`)
- Use `type(x)` or `isinstance(x, type)` to check an object’s type

## 11. Core Data Structures

Python has four core built-in collection types: `list`, `tuple`, `set`, and `dict`. These are the backbone of most Python programs.

> NOTE: This section covers the basics of using these data structures &mdash; enough to be productive and avoid surprises. Deeper topics (like comprehensions, unpacking, and iteration patterns) are covered later.

### 11.1. Lists

Lists are ordered, mutable sequences.

```python
fruits = ["apple", "banana", "cherry"]
```

- Indexable: `fruits[0] == "apple"`
- Mutable: `fruits[1] = "blueberry"`
- Append: `fruits.append("date")`
- Remove: `fruits.remove("banana")`
- Length: `len(fruits)`

Lists can contain any type, including other lists.

### 11.2. Tuples

Tuples are ordered, immutable sequences.

```python
point = (3, 4)
```

- Indexable: `point[0] == 3`
- Immutable: cannot reassign `point[1]`
- Often used for fixed-length groupings
- Parentheses are optional in many contexts: `x, y = 1, 2` defines a tuple

Single-element tuples require a trailing comma:

```python
one = (42,)  # this is a tuple
not_a_tuple = (42)  # just an int
```

### 11.3. Sets

Sets are unordered collections of unique values.

```python
nums = {1, 2, 3}
```

- No duplicates: `{1, 2, 2}` becomes `{1, 2}`
- Unordered: no index access
- Add: `nums.add(4)`
- Remove: `nums.remove(2)`
- Set operations: union (`|`), intersection (`&`), difference (`-`)

To make an empty set, use `set()`.  `{}` creates an empty `dict`.

### 11.4. Dictionaries

Dictionaries (or “dicts”) map keys to values.

```python
scores = {"Alice": 90, "Bob": 85}
```

- Keys must be hashable (e.g., strings, numbers, tuples)
- Values can be anything
- Access: `scores["Alice"]`
- Add/update: `scores["Charlie"] = 88`
- Remove: `del scores["Bob"]`
- Safe lookup: `scores.get("Dan", 0)`

Use `{}` to define a dict. To define an empty dict, use `{}` or `dict()`.

### 11.5. None

Python uses `None` to represent the absence of a value.

```python
value = None
```

- `None` is a singleton &mdash; only one instance exists
- Compare using `is` or `is not` (not `==`)
- Commonly used as:
  - Default values
  - Function return when there’s nothing else to return
  - Sentinel values

### 11.6. Summary

- Use `list` for general-purpose, ordered, mutable sequences.
- Use `tuple` for fixed-length, immutable groupings.
- Use `set` for unique unordered values.
- Use `dict` for key-value mappings.
- Use `None` to represent “no value”.

## 12. Functions And Parameter Passing

Functions in Python are defined using the `def` keyword. They support default arguments, keyword arguments, and flexible parameter unpacking.

### 12.1. Defining A Function

```python
def greet(name):
    print(f"Hello, {name}!")
```

- Functions use the `def` keyword and a colon to start a block.
- Indentation defines the function body.
- Functions return `None` by default if no `return` is given.

### 12.2. Returning Values

Use `return` to return a value:

```python
def square(x):
    return x * x
```

### 12.3. Default Parameters

You can provide default values:

```python
def greet(name, greeting="Hello"):
    print(f"{greeting}, {name}!")
```

Default arguments are evaluated once when the function is defined, not each time it is called.

⚠️ **Be careful with mutable defaults** (e.g., lists or dicts):

```python
def bad(x=[]):
    x.append(1)
    return x

print(bad())  # [1]
print(bad())  # [1, 1] — surprise!
```

Why this happens:  The default list is created once at definition time.  Each call to `bad()` that does not pass in arguments modifies this same list.

Instead, use `None` and assign inside the function:

```python
def good(x=None):
    if x is None:
        x = []
    x.append(1)
    return x
```

### 12.4. Positional And Keyword Arguments

This example refers back to the `greet` function of the previous section.  Arguments can be passed by position or keyword:

```python
greet("Alice", "Hi")                # positional
greet(name="Alice", greeting="Hi")  # keyword
greet(greeting="Hi", name="Alice")  # keyword order is flexible
```

- You can mix the two, but positional arguments must come first.
- Once you use a keyword argument, all remaining arguments must also be keywords.
- Keyword arguments can appear in any order.

### 12.5. Arbitrary Arguments

You can use `*args` and `**kwargs` to accept flexible arguments:

```python
def demo(*args, **kwargs):
    print("Positional:", args)
    print("Keyword:", kwargs)

demo(1, 2, 3, a=10, b=20)
```

- `*args` is a tuple of extra positional args
- `**kwargs` is a dict of extra keyword args

### 12.6. Parameter Passing Model

Python uses **pass-by-assignment** (a.k.a. “pass-by-object-reference”):

- Arguments are passed as references to objects.
- For **mutable objects**, changes inside the function **can affect** the original.
- For **immutable objects**, reassignment inside the function **does not affect** the original.

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

In Python, mutability is a property of the type.  Each built-in type is either mutable or immutable by design.  This cannot be controlled on a per-variable basis.

### 12.7. Summary

- Use `def` to define functions; they return `None` by default.
- Use `return` to return a value.
- Use default parameters with care.  Avoid mutable defaults.
- Arguments can be passed by position or keyword.
- Use `*args` and `**kwargs` for flexible parameters.
- Python passes arguments by object reference; mutability determines if changes affect the caller.  Mutability is a property of the type.
