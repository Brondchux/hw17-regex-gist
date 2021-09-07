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

_The OR operator, also known as alternation which is it's term in regular expression._

_In a regular expression it is denoted with a vertical line character_ **|**

_For instance, if we need to find the programming languages: HTML, PHP, Java or JavaScript._

_The corresponding regexp:_ html | php | java(script) ?.

_A usage example:_

```javascript
let regexp = /html|php|css|java(script)?/gi;

let str = "First HTML appeared, then CSS, then JavaScript";

console.log(str.match(regexp));
```

_Output_

```javascript
// 'HTML', 'CSS', 'JavaScript'
```

---

### Flags

_Regular expressions may have flags that affect the search.
There are only 6 of them in JavaScript:_

```javscript
"i"
```

_With this flag the search is case-insensitive: no difference between A and a._

```javscript
"g"
```

_With this flag the search looks for all matches, without it – only the first match is returned._

```javscript
"m"
```

_Multiline mode (covered in the chapter Multiline mode of anchors ^ $, flag "m")._

```javscript
"s"
```

_Enables “dotall” mode, that allows a dot . to match newline character \n._

```javscript
"u"
```

_Enables full Unicode support. The flag enables correct processing of surrogate pairs._

```javscript
"y"
```

_“Sticky” mode: searching at the exact position in the text._

---

### Character Escapes

_Let’s say we want to find literally a dot. Not “any character”, but just a dot._
_To use a special character as a regular one, prepend it with a backslash: `\`._

_That’s also called “escaping a character”._
_For example:_

```javascript
console.log("Chapter 5.1".match(/\d\.\d/)); // 5.1 (match!)
console.log("Chapter 511".match(/\d\.\d/)); // null (looking for a real dot \.)
```

_Parentheses are also special characters, so if we want them, we should use \(. The example below looks for a string "g()":_

```javascript
console.log("function g()".match(/g\(\)/)); // "g()"
```

_If we’re looking for a backslash \, it’s a special character in both regular strings and regexps, so we should double it._

```javascript
console.log("1\\2".match(/\\/)); // '\'
```

---

## Author

Name: Gospel Chukwu

Email: hello@gospelchukwu.com

Portfolio: [www.gospelchukwu.com](https://brondchux.github.io/hw2-my-portfolio/)
