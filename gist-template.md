  # REGEX Tutorial
Short for regular expression, a regex is a string of text that lets you create patterns that help match, locate, and manage text. Regular expressions can also be used from the command line and in text editors to find text within a file.

# Summary
This tutorial explains the use of a regular expression to match emails using the expression  `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. Regex like this can be used to validate email addresses using different applications and technologies. This tutorial will go through the components of the regex and explain their purpose.

# Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

# Regex Components

## Anchors
  The characters ^ and $ are examples of anchors. The ^ anchor signifies a string that begins with the characters that follow it. The $ anchor signifies a string that ends with the characters that precede it. Regex are case sensitive and so the case of the word that follows the ^ anchor is important. 

## Quantifiers
Quantifiers set the limits of the string that your regex matches. They frequently include the minimum and maximum number of characters that your regex is looking for. They match as many occurrences of particular patterns as possible. They include:

- *—Matches the pattern zero or more times

- +—Matches the pattern one or more times

- ?—Matches the pattern zero or one time

- {}—Curly brackets can provide three different ways to set limits for a match:

- { n }—Matches the pattern exactly n number of times

- { n, }—Matches the pattern at least n number of times

- { n, x }—Matches the pattern from a minimum of n number of times to a maximum of x number of times

By adding ? after any of these quantifiers it will match as few occurances as possible. 

## Grouping Constructs
As regular expressions grow more complicated, you may check multiple parts of a string to determine that different sections fulfill different requirements. To break these sections up, you'll need to use grouping constructs. The primary way you group a section of a regex is by using parentheses. Each section within parentheses is known as a subexpression. For example, (abc):(xyz) are subexpressions.

## Bracket Expressions
Anything inside a set of square brackets represents a range of characters that we want to match. They are also known as a positive character group, because they outline the characters we want to include. We can write these expressions to include all of the characters we want to match. For example, [abc] will look for a string that includes a or b or c, regardless of the length of the string. You'll commonly see a hyphen used between alphanumeric characters  to represent a range of those possible characters. This means that [a-c] and [abc] will look for the exact same thing. This can be seen in the example above where there is [a-z].

## Character Classes
A character class in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match. Some examples of common character classes include:

- .—Matches any character except the newline character (\n)

- \d—Matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9].

- \w—Matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [a-z0-9_].

- \s—Matches a single whitespace character, including tabs and line breaks

## The OR Operator
Using the OR operator (|), the expression [abc] could be written as (a|b|c). Using our example in the grouping constructs section, we can  use the OR operator to convert (abc):(xyz) to (a|b|c):(x|y|z). Now, both of the strings "abc:xyz" and "acb:xyz" would match, as well as "a:z", but "xyz:abc" would not.

## Flags
Normally a regex must be wrapped in slash characters, the only exception to this rule is with the component known as flags. Flags are placed at the end of a regex, after the second slash, and they define additional functionality or limits for the regex. There are six optional flags that can be used, either separately or together and in any order, but the three commonly used flags are:

- g—Global search: the regex should be tested against all possible matches in a string.

- i—Case-insensitive search: case should be ignored while attempting a match in a string

- m—Multi-line search: a multi-line input string should be treated as multiple lines

## Character Escapes
The backslash in a regex escapes a character that otherwise would be interpreted literally. For example, the open curly brace ({) is used to begin a quantifier, but adding a backslash before the open curly brace (\{) means that the regex should look for the open curly brace character instead of beginning to define a quantifier. This is common when looking for strings with special characters that are the same as a particular component of a regex. All special characters, including the backslash, lose their special significance inside bracket expressions.
