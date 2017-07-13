# Python Fundamentals
A repo for notes, example code, etc. from the Python Fundamentals course by Austin Bingham and Robert Smallshire on PluralSight

Some of interesting properties of Python:

* Duck Typed
* General Purpose
* Interpreted (compiled to intermediate bytecode transparently)
* Clear, Readable, and Expressive -- space delimited, no parentheses
* CPython - written in C - typical and popular version
    * Other Implementations:
        * Jython -> Java -- compiled to Java bytecode, interoperable with Java
        * IronPython -> .NET -- interoperable with .NET framework libraries
        * pypy -> RPython -- high performance, statically-typed subset of CPython
* Two Versions
    * Python 2 and Python 3
* Batteries Included -- robust Python Standard library

## Module 1: Getting Started

### Significant Whitespace

* Requires readable code
* No clutter
* Human and computer can't get out of sync

### Significant Whitespace Rules

* Prefer four (4) spaces; instead of tabs
* Never mix tabs and spaces
* Be consistent on consecutive lines
* Only deviate to improve readability

### Python Culture and the Zen of Python

* Management of the language is done through Python Enhancement Proposals (PEPs)
* PEP 8 - provides guidance on the style for Python Code
* PEP 20 - Zen of Python; `import this` from the REPL
* Batteries Included -> Python Standard Library

### Importing from the Python Standard Library

In Python you have few different options when you want to import a module from the Python Standard Library.

* import statement
    * usage: `import math`
    * example: `math.sqrt(4)`
* from ... import statement
    * usage:  `from math import sqrt`
    * alt usage: `from math import sqrt as square_root`
    * example: `sqrt(4)` or `square_root(4)`

## Module 2: Strings and Collections



## Module 3: Modularity



## Module 4: Built-in Types and the Object Model



## Module 5: Collection Types



## Module 6: Handling Exceptions



## Module 7: Comprehensions, Iterables, and Generators



## Module 8: Defining New Types with Classes



## Module 9: Files and Resource Management



## Module 10: Shipping Working and Maintainable Code
