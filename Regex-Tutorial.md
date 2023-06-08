# Regex-Tutorial.md
## Summary

A Regex or regular expression is a sequence of characters that define a search pattern. Usually, such patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings. It also looks for input validations. It is a technique commonly developed in theoretical computer science.

We will look a string of code using regex, this code looks for a match HTML tag.

Example: `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`

The below content will explain what each section of this code does and more.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)
- [Author](#Author)
- [Sources&Refrences](#Sources&Refrences)

## Regex Components

### Anchors

* `^abc$` - ^start / $end of the string
    * `^` Matches the beginning of the string, or the beginning of a line if the multiline flag (m) is enabled. This matches a position, not a character.
    * `$` Matches the end of the string, or the end of a line if the multiline flag (m) is enabled. This matches a position, not a character.

* `\b\B` - word, not-word boundary
    * `\b` Matches a word boundary position between a word character and non-word character or position (start / end of string). See the word character class (w) for more info.
    * `\B` Matches any position that is not a word boundary. This matches a position, not a character.
    * See Boundaries for more detailed Information

### Quantifiers

Quantifiers indicate that the preceding token must be matched a certain number of times. A quantifier can be greedy or lazy, which is explained below.

* `a*a+a?` - 0 or more, 1 or more, 0 or 1
    * "+" Matches 1 or more of the preceding token.
    * "*" Matches 0 or more of the preceding token.
    * "?" Matches 0 or 1 of the preceding token, effectively making it optional.
    * "?" Makes the preceding quantifier lazy, causing it to match as few characters as possible. By default, quantifiers are greedy and will match as many characters as possible.

* `a{5}a{2,}` - Looks for exactly five, two or more
* `{2,6}` - forces the input of characters between two & six characters long.
* `a+?a{2,}?` - match as few as possible
* `ab|cd` - match ab or cd

### OR Operator

* `|` Acts like a boolean OR. Matches the expression before or after the |.
It can operate within a group or on a whole expression. The patterns will be tested in order. Just as in java will match either set of characters. It will look for this OR that.

### Character Classes

Character classes match a character from a specific set. There are a number of predefined character classes, and you can also define your own sets.

* `[ABC]` Characters inside brackets
* `[^ABC]` Characters not inside brackets
* `[0-9]` or `[a-z]` or `[A-Z]` Matches a character in the specified range
* `[abc][vz]` Matches a single character, that is either a, b, or c followed by either v or z
* `[0-9a-fA-F]` Matches a digit or a character that is a hexadecimal digit (lowercase or uppercase)
* `[a-zA-Z0-9_]` Matches a word character (alphanumeric or underscore)

### Flags

Flags are used to enable various matching options. They are placed directly after the closing delimiter of the regular expression and can change how the pattern is interpreted.

* `g` - Global search
    * The pattern will continue to search for all matches in the input string, rather than stopping after the first match.

* `i` - Case-insensitive search
    * The pattern will match both uppercase and lowercase letters.

* `m` - Multiline search
    * The pattern will match the start and end of each line within the input string. By default, ^ and $ match the start and end of the whole string.

### Grouping and Capturing

Grouping and capturing allow you to create logical units within a regular expression. Captured groups can be extracted for further processing or used for back-references.

* `(abc)` - Capture Group
    * Parentheses are used to capture and group substrings.
    * The first set of parentheses captures and remembers the matched string.
    * Captured groups can be used for back-references or extracted for further processing.

* `(?:abc)` - Non-capturing Group
    * Parentheses are used to group substrings but do not capture the matched string.
    * Non-capturing groups are useful when you want to apply a quantifier to a group but do not need to extract the group's value.

### Bracket Expressions

Bracket expressions allow you to match a single character from a specific set of characters. They are enclosed in square brackets.

* `[abc]` - Matches a single character that is either a, b, or c.
* `[0-9]` - Matches a single digit between 0 and 9.
* `[^abc]` - Matches a single character that is not a, b, or c.

### Greedy and Lazy Match

Quantifiers can be greedy or lazy. Greedy quantifiers match as many instances of the quantified token as possible, while lazy quantifiers match as few instances as needed.

* `a+` - Greedy match (matches as many "a" as possible).
* `a+?` - Lazy match (matches as few "a" as possible).

### Boundaries

* `\b` - Word boundary
    * Matches a word boundary position (position between a word character and a non-word character) or the position between a word character and the start or end of the string.

* `\B` - Not a word boundary
    * Matches any position that is not a word boundary.

### Back-references

Back-references allow you to refer back to previously captured groups within the regular expression.

* `\1` - Back-reference to the first captured group.
    * The backslash followed by a digit n, where n is a positive integer, matches the same text as the nth captured group.

### Look-ahead and Look-behind

Look-ahead and look-behind assertions allow you to match a pattern only if it is followed or preceded by another pattern, without including the other pattern in the final match.

* `(?=abc)` - Positive look-ahead
    * Matches the preceding expression only if it is followed by abc.

* `(?!ABC)` - Negative look-ahead
    * Matches the preceding expression only if it is followed by abc.

* `(?<=abc)` - Positive look-behind
    * Matches the preceding expression only if it is preceded by abc.

* `(?<!ABC)` - Negative look-behind
    * Matches the preceding expression only if it is preceded by abc.

For more detailed information on regular expressions, please refer to the official documentation or other reliable resources.

### Author

Joaquin Loya: Student at UCLA Coding Bootcamp

###Sources&Refrences

* [regexr](https://regexr.com/)
* [BackRef](https://www.regular-expressions.info/backref.html)
* [RegExpression](https://www.regular-expressions.info/wordboundaries.html)

My Github [github] https://github.com/JLoya900