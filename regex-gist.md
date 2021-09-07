# Regex for Beginners 101

Do characters like ("<?>%/-_#/_$) confuse you? If yes then this gist project was created for you.
We will cover what Regular Expression (regex) is about starting from the basics.
Excited to learn and understand regex? Let's get started!

## Summary

A regular expression (shortened as regexp; also referred to as rational expression or regex) is a sequence of characters that specifies a search pattern. Usually such patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings, or for input validation.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

_Anchors assert that the engine's current position in the string matches a well-determined location: for instance, the beginning of the string, or the end of a line.
See the following example:_

```javascript
let str = "Gospel";
console.log(/^G/.test(str));
```

_Output_

```javascript
true;
```

_The /^J/ match any text that starts with the letter J. It returns true_

### Quantifiers

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

Name: Gospel Chukwu

Email: hello@gospelchukwu.com

Portfolio: [www.gospelchukwu.com](https://brondchux.github.io/hw2-my-portfolio/)
