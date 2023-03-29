# Regular Expression (REGEX)

A regex, which is short for regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input.

## Summary

Regular expressions can be used for all types of text-based manipulation tasks, but it is mainly used for matching, replacement and extraction. Regular expressions can be used to find text that matches a pattern, replace matched text with other text, or extract certain portions of the text for later use. Take the following example of a regular expression, which we’ll call "Matching and Email" or "Validate Email Address".

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

In the above example, it can be look into a series of /^([a-z0-9_\.-]+) followed by @ sign, and then followed by ([\da-z\.-]+)\, then finally follwed with a dot and ([a-z\.]{2,6})$/. This is literally an email address.


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
A regex is considered a literal, so the pattern must be wrapped in slash characters (/). 

### Anchors
The characters ^ and $ are both considered to be anchors. The ^ anchor signifies a string that begins with the characters that follow it and the $ anchor will be the end of string. For examples:

^The end$   exact string match (starts and ends with The end)

### Quantifiers
Quantifiers set the limits of the string that the regex matches (or an individual section of the string). They frequently include the minimum and maximum number of characters that the regex is looking for. Quantifiers are inherently greedy, meaning they match as many occurrences of particular patterns as possible. Let see at part of our regex code 

.([a-z\.]{2,6})

This regex {2,6} is looking for any string between 2 and 6 characters. The quantifiers include * + ? and {}. 

### Grouping Constructs
As regular expressions grow more complicated, it's important to check multiple parts of a string to determine that different sections fulfill different requirements. To break these sections up, we'll need to use grouping constructs.

The primary way to group a section of a regex is by using parentheses (()). Each section within parentheses is known as a subexpression and in our case, the regex is divided by three sections: ([a-z0-9_\.-]+), ([\da-z\.-]+), and ([a-z\.]{2,6}).

### Bracket Expressions
A bracket expression is a list of characters enclosed by ‘[’ and ‘]’. It matches any single character in that list. If the first character of the list is the caret ‘^’, then it matches any character not in the list, and it is unspecified whether it matches an encoding error. For example, the regular expression ‘[0123456789]’ matches any single digit.

### Character Classes
A character class in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match. The most charcter clsses are:

.—Matches any character except the newline character (\n)

\d—Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].

\w—Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [A-Za-z0-9_].

\s—Matches a single whitespace character, including tabs and line breaks

Each of the last three character classes can be changed to perform an inverse match by capitalizing the letter character. For example, \D matches a non-digit character.

### The OR Operator
Remember that a bracket expression does not require the string to meet all of the requirements in the pattern. This means that [a-z0-9_-] searches for alphanumeric characters or the two special characters included in the pattern. Often, we'll want to add this same logic outside of a bracket expression, especially within a grouping construct or between two different grouping constructs.

Using the OR operator (|), the expression [abc] could be written as (a|b|c). 

### Flags
A regex usually comes within this form /abc/, where the search pattern is delimited by two slash characters /. At the end we can specify a flag with these values (we can also combine them each other):

g (global) does not return after the first match, restarting the subsequent searches from the end of the previous match
m (multi-line) when enabled ^ and $ will match the start and end of a line, instead of the whole string
i (insensitive) makes the whole expression case-insensitive (for instance /aBc/i would match AbC)

### Character Escapes
The backslash (\) in a regex escapes a character that otherwise would be interpreted literally. For example, the open curly brace ({) is used to begin a quantifier, but adding a backslash before the open curly brace (\{) means that the regex should look for the open curly brace character instead of beginning to define a quantifier. This is common when looking for strings with special characters that are the same as a particular component of a regex.

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
