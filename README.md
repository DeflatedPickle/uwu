## Contents
- [Introduction](#introduction)
- [Packages](#packages)
  - [Package Naming](#package-naming)
- [Files](#files)
  - [File Naming](#file-naming)
  - [Main File](#main-file)
  - [File Formatting](#file-formatting)
  - [Line Ending](#line-ending)
- [Comments](#comments)
  - [Inline](#inline)
    - [Trailing](#trailing)
  - [Block](#block)
    - [Embedded](#embedded)
    - [Docstring](#docstring)
- [Variables](#variables)
- [Functions](#functions)
- [Classes](#classes)
  - [Properties](#properties)
  - [Methods](#methods)
- [Enums](#enums)

### Introduction
This is a simple style guide to follow when writing code. It serves as any style guide does, to format code in a way that people want to read. Of course, like most style guides, its contents is trivial and most people will dislike certain parts, as is with any style guide.

For the rest of this page, I'll be using the Kotlin and Python language's to show examples, but I'll (hopefully) explain in a way that applies to any language, with esoteric ones being an exception.

This style guide should **not** be used as a replacement if the language has an official style guide. People know that style, so use it. The same goes for hugely popular style guides that aren't official to the language but are to the community.

---

### Packages
#### Package Naming
Package names should be lowercase.

---

### Files
##### Main File
A program should always have a main file, unless it's a script (then it's the only file).

The main file of a program, unless containing an class/class-like object, should be named "`main`" (in lowercase). If it does contain a class or class-like object, that should be named "`Main`".

##### File Naming
Files should be named after what they contain, in the same case. For instance, if a file contains the class "`Foo`", the file should also be called "`Foo`". And if it contains a fuction called `fooBar`, the file should be named as such.

#### File Formatting
Files should be formatted with tabs, which should be as wide as four spaces.

#### Line Ending
If the language requires syntax to end a line, use it. If it doesn't, don't.

---

### Comments
Comments should not come after syntax that creates a block. Either they are placed before the block, to describe it. Or placed inside the block, to describe other lines.

#### Line
Line comments should start at the current tab level if they are the only thing on the line, as it's easier to gather the context if the code and comments have the same indentation.

##### Kotlin:
```kotlin
// A function
fun myFunc() {
  // Prints "Hello, World!"
  println("Hello, World!")
}
```

##### Python:
```python
# A function
def myFunc():
    # Prints "Hello, World!"
    print("Hello, World!")
```

#### Trailing
Trailing comments don't look good. Don't use them.

#### Block
Block comments should, like inline comments, start at the current tab level if they're on their own. Each line of the comment should start with the second character, if the syntax spans two characters, to align each line. The ending syntax should also be indented by a space, if the syntax spans two characters, to align them.

##### Kotlin:
```kotlin
/*
 * A function.
 */
fun myFunc() {
}
```

##### Python:
```python
#
# A function.
#
def myFunc():
    pass
```

##### Embedded
Embedded/in-line comments should be padded on the inside and outside by one space.

##### Kotlin:
```kotlin
fun myFunc(name: /* Int */ String) {
  println("Hello, ${name}!")
}
```

##### Docstring
Docstrings, are similar to normal block comments, unless the language has specific syntax/methods for docstrings, however the beginning syntax ends with two of the second character. They should include all parameters, the return type and provide see tags to any classes referenced that aren't provided by the language.

##### Kotlin:
```kotlin
/**
 * Does nothing.
 *
 * @return Nothing
 */
fun myFunc() {
}
```

##### Python:
```python
def myFunc():
    """
    Does nothing.
    
    @return Nothing
    """
    pass
```

---

### Variables
If a variable is only used once, it should be defined as constant to save memory. The type of the variable should also be specified on creation, even if the language doesn't require it, unless it's made clear what type it is.

#### Mutable
Mutable variable names should be in lowercase, with words seperated by underscores.

##### Kotlin:
```kotlin
var my_variable: String = "Hello, World!"
my_variable = "Good bye, World!"
```

##### Python:
```python
my_variable: str = "Hello, World!"
my_variable = "Good bye, World!"
```

#### Constant
Constant variable names should be in all-caps, like you forgot to turn off caps-lock, though actually, you wanted it on. Words, like mutable variable names, should be seperated by underscores.

##### Kotlin:
```kotlin
val MY_VARIABLE: String = "Hello, World!"
```

##### Python:
```python
MY_VARIABLE: str = "Hello, World!"
```

---

### Functions
Functions should always have an attached docstring describing what it; does, returns and what the parameters do -- but only if the source is open. The return type of functions should always be specified, and the parameter types should always be specified. If the language allows for it, resonable default values for parameters should be specified if the parameter is not crutial to the users choice.

##### Kotlin:
```kotlin
/**
 * Prints "Hello" followed by a given name.
 *
 * @param  name The name to say 'Hello' to
 * @return      Nothing
 */
fun myFunc(name: String): Unit {
  println("Hello, ${name}!")
}
```

##### Python:
```python
def myFunc(name: str) -> None:
    """
    Prints "Hello" followed by a given name.
    
    @param name The name to say 'Hello' to
    @return     Nonthing
    """
    print(f"Hello, {name}")
```

---

### Classes
Classes, like functions, should always have a docstring to describe it and what it's used for, if the source is open, even if the class is private or package-private. They should be named with each new word starting with an uppercase letter, with the rest of the word being lowercase.
If the class is public, it must provide a public constructor.

##### Kotlin:
```kotlin
/**
 * Creates a vector of two values.
 */
class Vector2<T> {
  /**
   * Constructs an instance, providing the x and y.
   * 
   * @param x Where the point is on the X axis
   * @param y Where the point is on the Y axis
   */
  constructor(val x: T, val y: T) {
  }
}
```

##### Python:
```python
class Vector2(object):
   """
   Creates a vector of two values.
   """
   
   def __init__(x, y):
       """
       Constructs an instance, providing the x and y.
       
       @param x Where the point is on the X axis
       @param y Where the point is on the Y axis
       """
       pass
```

#### Properties

#### Methods

---

### Enums
Enums, like classes and functions, should always have a docstring to describe it, if the source is open, even if the enum is private.

#### Prefix
Unless the language uses a diffrent file extension for them, enum names should always begin with a capital "`E`" to differentiate them from classes at the file level.

##### Kotlin:
```kotlin
/**
 * An enum for the primary colours.
 */
enum class EPrimaryColour {
    RED,
    YELLOW,
    BLUE
}
```

##### Python:
```python
from enum import Enum

class EPrimaryColour(Enum):
    RED = 1
    YELLOW = 2
    BLUE = 3
```

---
