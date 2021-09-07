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

_The /^G/ match any text that starts with the letter J. It returns true_

---

### Quantifiers

_Quantifiers match a number of instances of a character, group, or character class in a string._

_Exact count {n}. A number in curly braces {n}is the simplest quantifier. When you append it to a character or character class, it specifies how many characters or character classes you want to match._

_For example, the regular expression /\d{4}/ matches a four-digit number. It is the same as /\d\d\d\d/:_

```javascript
let str = "ECMAScript 2020";
let re = /\d{4}/;

let result = str.match(re);

console.log(result);
```

_Output_

```javascript
["2020"];
```

---

### Grouping Constructs

_A part of a pattern can be enclosed in parentheses (...). This is called a “capturing group”._

_That has two effects:_

1. _It allows to get a part of the match as a separate item in the result array._
2. _If we put a quantifier after the parentheses, it applies to the parentheses as a whole._

_For Example, email format is: name@domain. Any word can be the name, hyphens and dots are allowed. In regular expressions that’s [-.\w]+._

```javascript
let regexp = /[-.\w]+@([\w-]+\.)+[\w-]+/g;

console.log("my@mail.com @ his@site.com.uk".match(regexp));
```

_Output_

```javascript
// my@mail.com, his@site.com.uk
```

---

### Bracket Expressions

_Brackets indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set._

```javascript
"elephant".match(/[abcd]/); // -> matches 'a'
```

_You will often see ranges of the alphabet or all numerals. [A-Za-z] [0-9] Remember that these character sets are case sensitive, unless you set the i flag._

```javascript
"elephant".match(/[a-d]/); // -> matches 'a'
"elephant".match(/[A-D]/); // -> no match
"elephant".match(/[A-D]/i); // -> matches 'a'
```

---

### Character Classes

_A character class allows you to match any symbol from a certain character set. A character class is also called a character set. Suppose that you have a phone number like this:_

```javascript
"+1-(408)-555-0105";
```

_Now, you can turn the phone number into a plain number as follows:_

```javascript
let phone = "+1-(408)-555-0105";
let re = /\d/g;

let numbers = phone.match(re);
let phoneNo = numbers.join("");

console.log(phoneNo); // -> 14085550105
```

---

### The OR Operator

### Flags

### Character Escapes

## Author

Name: Gospel Chukwu

Email: hello@gospelchukwu.com

Portfolio: [www.gospelchukwu.com](https://brondchux.github.io/hw2-my-portfolio/)
