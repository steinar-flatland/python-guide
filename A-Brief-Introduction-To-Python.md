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
- Accidentally misaligning a line will silently alter logic &mdash; Python won’t warn if the indentation is syntactically valid but semantically wrong.

## 3. Comments
