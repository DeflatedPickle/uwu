## Contents
- [Introduction](#introduction)
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

### Introduction
This is a simple style guide to follow when writing code. It serves as any style guide, to format code in a way that people want to read. Of course, like most style guides, its contents is trivial and most will dislike certain parts, as-is with any style guide.

For the rest of this page, I'll be using the Kotlin language to show examples, but I'll (hopefully) explain in a way that applies to any language, with esoteric ones being an exception.

This style guide should **not** be used as a replacement if the language has an official style guide. People know that style, so use it. The same goes for hugely popular style guides that aren't official to the language but are to the community.

---

### File Formatting
Files should be formatted with tabs, which should be as wide as four spaces.

---

### Line Ending
If the language requires syntax to end a line, use it. If it doesn't, don't.

---

### Comments
Comments should not come after syntax that creates a block. Either they are placed before the block, to describe it. Or placed inside the block, to describe other lines.
#### Line
Line comments should start at the current tab level if they are the only thing on the line.
```kotlin
// A function
fun myFunc() {
  // Prints "Hello, World!"
  println("Hello, World!")
}
```
##### Trailing
Trailing comments should follow two spaces.
```kotlin
fun myFunc() {
  println("Hello, World!")  // Prints "Hello, World!"
}
```
#### Block
Block comments should, like inline comments, start at the current tab level if they're on their own. Each line of the comment should start with the second character, if the syntax spans two characters, to align each line. The ending syntax should also be indented by a space, if the syntax spans two characters, to align them.
```kotlin
/*
 * A function.
 */
fun myFunc() {
}
```
##### Embedded
Embedded comments should be padded on the outside by two spaces and on the inside by one.
```kotlin
fun myFunc(name:  /* Int */  String) {
  println("Hello, ${name}!")
}
```
##### Docstring
Docstrings, are similar to normal block comments, however the beginning syntax ends with two of the second character. They should include all parameters, the return type and provide see tags to any classes referenced that aren't provided by the language.
```kotlin
/**
 * Does nothing.
 *
 * @return Nothing
 */
fun myFunc() {
}
```
---

### Variables
If variables are only used once, they should be defined as constant to save memory. The type of the variable should also be specified on creation, even if the language doesn't require it.
#### Mutable
Mutable variable names should begin with a lowercase letter, with uppercase letters for the beginning of each word after the first, with words seperated by underscores.
```kotlin
var my_variable: String = "Hello, World!"
my_variable = "Good bye, World!"
```
#### Constant
Constant variable names should be in all-caps, like you forgot to turn off caps-lock, though actually, you wanted it on. Words, like mutable variable names, should be seperated by underscores.
```kotlin
val MY_VARIABLE: String = "Hello, World!"
```
---

### Functions
Functions should always have an attached docstring describing what it; does, returns and what the parameters do. The return type of functions should always be specified, and the parameter types should always be specified. If the language allows for it, resonable default values for parameters should be specified if the parameter is not crutial to the users choice.
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
---

### Classes
Classes, like functions, should always have a docstring to describe it and what it's used for. They should be named with each new word starting with an uppercase letter, with the rest of the word being lowercase.
If the class is public, it must provide a public constructor.
```kotlin
/**
 * Creates a vector of two values.
 */
open class Vector2<T> {
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
#### Properties

#### Methods
---
