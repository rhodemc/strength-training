# Strength Training: A Regex Tutorial on Password Strength

In the modern world, data breaches are an almost every day occurence. For your own security, it is important to know how to create a strong password so that your most private data doesn't get exposed.

## Summary

This tutorial will help you understand how to use regular expressions to test and produce a moderately strengthed password.

Before diving into a specific example however, it is important to understand the basics of regular expressions. A regular expression is a sequence of characters that define a search pattern. They are used to find, replace, and validate text. Regular expressions are universal and can be used in both text editors and programming languages, including JavaScript, Python, and Ruby, to name a few.

Below is the regular expression, or regex, that will be used to test your password strength. It looks for a string that is at least 8 characters long and contains at least one uppercase letter, one lowercase letter, and one number:

`/(?=(.*[0-9]))((?=.*[A-Za-z0-9])(?=.*[A-Z])(?=.*[a-z]))^.{8,}$/`

## Table of Contents

- [Strength Training: A Regex Tutorial on Password Strength](#strength-training-a-regex-tutorial-on-password-strength)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
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
  - [Author](#author)

## Regex Components

### Anchors

`^.{8,}$`

Anchors are used to signal a position before or after characters. The regex used in this tutorial uses two anchors: `^` and `$`. The `^` anchor signals the beginning of the string, while the `$` anchor signals the end of the string.

### Quantifiers

`^.{8,}$`

Inside the above anchors is a quantifier. Quantifiers are used to specify the number of characters or expressions to match. Greedy expressions will match as many occurrences as possible. Adding a `?` will create a lazy expression, matching as few occurrences as possible.

The regex used in this tutorial uses the quantifier: `{8,}`. `{8,}` quantifier means the password must match the preceding bracket expressions 8 or more times depending on the length of the string.

### OR Operator

This regex does not use an OR operator.

### Character Classes

Character classes define a set of characters to match. The regex used in this tutorial uses the following character classes:

`.`: Matches any character except line breaks.

`*`: Matches the preceding expression 0 or more times.

Bracket expressions are also considered character classes, but we will discuss those in greater detail below.

### Flags

Flags are used to perform case-insensitive, multi-line and global searches. The regex used in this tutorial does not use any flags.

### Grouping and Capturing

Grouping constructs are are created by placing the characters to be grouped inside a set of parentheses. The regex used in this tutorial uses grouping to define subexpressions of allowable characters in the password. For example:

`(?=(.*[A-Za-z0-9]))`

The groups in this regex are considered non-capturing. `?=` is used to specify each group as such and will not capture characters for potential re-use. `?=` is also known as a positive lookahead, which we'll discuss later in this tutorial.

For reference, capturing groups capture matched sequences for potential later use. The regex used in this tutorial does not use capturing groups.

### Bracket Expressions

Bracket expressions make up most of our example regex. They are used to define a set of characters to match. The regex used in this tutorial uses the following bracket expressions:

`[0-9]`: Matches any digit between 0 and 9.

`[A-Za-z0-9]`: Matches any uppercase letter, lowercase letter, or digit.

`[A-Z]`: Matches any uppercase letter.

`[a-z]`: Matches any lowercase letter.

Bracket expressions are also considered character classes, which was discussed above.

### Greedy and Lazy Match

Greedy expressions will match as many occurrences as possible. Adding a `?` will create a lazy expression, matching as few occurrences as possible. This regex uses greedy expressions.

`^.{8,}$`

In our example, the `{}` define the quantifier as greedy. It will match as many characters as possible, but will not match less than 8.

### Boundaries

Boundaries are used to match a position before or after specified characters. The regex used in this tutorial does not use boundaries.

### Back-references

Back-references are used to match the same text as previously matched by a capturing group. The regex used in this tutorial does not use back-references.

### Look-ahead and Look-behind

Look-ahead is used to match characters that are followed by a specified pattern. Look-behind is used to match characters that are preceded by a specified pattern.

The regex used in this tutorial uses look-ahead to match the following patterns, or bracket expressions:

`(?=(.*[0-9]))`: Matches any character followed by a digit.

`(?=(.*[A-Za-z0-9]))`: Matches any character followed by an uppercase letter, lowercase letter, or digit.

`(?=(.*[A-Z]))`: Matches any character followed by an uppercase letter.

`(?=(.*[a-z]))`: Matches any character followed by a lowercase letter.

## Author

Rhodemc is a full-stack web developer based in the United States. You can find him on [GitHub](https://github.com/rhodemc/).
