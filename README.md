## Contents
- [Comments](#comments)
  - [Inline](#inline)
  - [Block](#block)
    - [Docstring](#docstring)
- [File Formatting](#file-formatting)

### Comments
#### Inline
Inline comments should start at the current tab level if they are the only thing on the line;
```kotlin
// A function
fun my_func() {
  // Prints "Hello, World!"
  print("Hello, World!")
}
```
But if they follow code, they should follow after two spaces;
```kotlin
fun my_func() {  // A function
  print("Hello, World!")  // Prints "Hello, World!"
}
```
#### Block
Block comments should, like inline comments, start at the current tab level if they're on their own. Each line of the comment should start with the second character, if the syntax spans two characters, to align each line. The ending syntax should also be indented by a space, if the syntax spans two characters, to align them.
```kotlin
/*
 * A function.
 */
fun my_func() {
}
```
##### Docstring
Docstrings, are similar to normal block comments, however the beginning syntax ends with two of the second character.
```kotlin
/**
 * Does nothing.
 */
fun my_func() {
}
```
### File Formatting
Files should be formatted with tabs, which should be as wide as four spaces.
