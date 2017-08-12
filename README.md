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

### Scalar types and values

* int
* float
* None
* bool

You can use the constructors of the Scalar types to convert from one type to another.

Example:

float(7) will return 7.0

float("7") will return 7.0

None is like null from other languages

You can use the bool constructor to determine whether a value is truthy or falsy

Example:

bool(0) will return False

bool(42) will return True

All non-zero, positive or negative ints and floats will return True; zero ints and floats will return False

You can also use the bool constructor to determine whether a collection is truthy or falsy

Example:

bool([]) will return False

bool([1, 5, 9]) will return True

You can also use the bool constructor to determine whether a string is truthy or falsy

Example:

bool("") will return False

bool("Kevin") will return True

However, you can NOT convert string representations of a bool, so this won't work:

bool("False") will NOT return False but True because it is a non-empty string

bool("True") will return True, but not because it can convert the string into a bool; same reason as above

### Relational (Comparison) Operators

Python has a standard set of relational operators

`==` - value equality or equivalence

`!=` - value inequality or inequivalence

`<` - less than

`>` - greater than

`<=` - less than or equal to 

`>=` - greater than or equal to 

### Conditional Statements

#### If Statements

Python has a standard if statement - simply an if with some expresion and a colon with the contents of the if statement indented 4 spaces and the a blank line following the statement.  

Here are some examples of if statments:

```python
if somexpr:
    print("It's true")

if False:
    print("It's true")

if bool("eggs"):
    print("Yes please")

if "eggs":
    print("Yes please")
    
```

And here are some examples of if else statements:

```python
if h > 50:
    print("Greater than 50")
else:
    print("Less than 50")
```

As far as nested if statements, Python offers an alternative in order to avoid nest ifs:

```python
### nested if statement ###

if h > 50:
    print("Greater than 50")
else:
    if h < 20:
        print("Less than 20")
    else:
        print("Between 20 and 50")

### pythonic alternative - elif statement ###

if h > 50:
    print("Greater than 50")
elif h < 20:
    print("Less than 20")
else:
    print("Between 20 and 50")
```

### While Loops

Python contains a standard while loop, whereby you use the while keyword followed by an expression, a colon, and then a statement inside the loop.  Note the expression is converted to bool as if done by the bool constructor.  You can use the break keyword to trigger existing an "infinite" loop.

Example:

```python
while someexpr:
    print("loop while expr is True")
    
while True:
    if expr:
        break
print("Go here on break")
```

## Module 2: Strings and Collections

* str
* bytes
* list
* dict

### Strings

Strings are immutable in Python and can be quoted using either single or double quotes.

Adjacent quoted strings are concatenated by Python

Example:

"first" "second" becomes "firstsecond"

The string constructor, like other constructors in Python, can be used to convert other types into strings.

Example:

str(496) will return '496'

str(6.02) will return '6.02'

#### Strings with Newlines

Three double or single quotes can be used to do multiline strings

Example:

"""This is

a multiline

string"""

This is echoed back as:

'This is \na multiline\nstring'

The \n new line characters embedded in the string

As an alternative, you can simply place the \n characters in a string to achieve the same effect in Python.

Example:

"This is \na multiline\nstring" would be rendered the same as above on multiple lines

NOTE:  \n is multi-platform - called Universal Newlines in Python 3 - so \n on Windows gets converted automagically by Python into \r\n  This is from PEP 278.

#### Escape Sequences

Like many languages Python supports a variety of escape sequences in order to be able to render special characters in a string.  \n and \t are just a couple of examples. 

#### Raw Strings

In order to handle things like URLs or file paths in Python there is the concept of a raw string.

Example:

```python
path = r'C:\some\path\in\the\file\system'
```

Path would be rendered by Python's `print` command like this:

```python
'C:\some\path\in\the\file\system'
```

#### Strings as sequence types

Strings are sequence types in Python, meaning that certain operations can be done automagically against a string -- for querying sequences.  Because of this feature, in Python there isn't a separate concept of a character type.  In the example below the string characters can be accessed via a 0 based index.

Examples:

```python
s = 'parrot'
s[4] ### would render 'o' ###

```

### Bytes

Immutable sequences of bytes

#### Bytes Literals

b'data' or b"data"

### Lists

Mutable sequences of objects

Delimited by square brackets

Examples:

```python
[1, 9, 8]

["apple", "orange", "pear"]

['apple', 7, 'pear']

### you can create an empty list and then use the append method to add things to it ###
b = []
b.append(1.618)
b.append(1.414)

### would result in ###
[1.618, 1.414]

### list constructor ###

list("characters")

### would result in ###
['c', 'h', 'a', 'r', 'a', 'c', 't', 'e', 'r', 's']

### you can take advantage of white space is Python to make long lists readable
animals = ['bear', 
           'giraffe',
           'elephant',
           'caterpillar',]

### would result in ###
['bear', 'giraffe', 'elephant', 'caterpillar']
```

### Dictionary

Mutable mappings of keys to values

#### Dict Literals

```python
{k1: v1, k2: v2}
```

### For Loop

Similar to a For Each loop from other languages.

Follows the pattern:

```python
for item in iterable:
  ### body of the loop ###

### iterate over a list ###
cities = ["London", "New York", "Paris", "Oslo", "Helsinki"]

for city in cities:
  print(city)
  
### would result in ###
London
New York
Paris
Oslo
Helsinki

### iterate over a dict ###
colors = {'crimson': 0xdc143c, 'coral': 0xff7f50, 'teal': 0x00}

### we get the keys when looping so in turn we can use the keys to retrieve the associated values ###
for color in colors:
  print(color, colors[color])
  
### would result in ###
coral 16744272
teal 32896
crimson 14423100 
```




## Module 3: Modularity



## Module 4: Built-in Types and the Object Model



## Module 5: Collection Types



## Module 6: Handling Exceptions



## Module 7: Comprehensions, Iterables, and Generators



## Module 8: Defining New Types with Classes



## Module 9: Files and Resource Management



## Module 10: Shipping Working and Maintainable Code
