# Regex Tutorial - Matching an Email

This tutorial goes over a brief explanation of of what regex are and specifically the use of regex to match emails using the expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. This would be a great way to validate emails when using technologies that allow the use of regex such as JavaScript, Java, C, C++, or Python.

## Summary

A regex, or a regular expression, is a sequence of characters used to find patterns or replace characters within a string or input. This tutorial will go through the components that can be found in a regex and how they apply to matching an email. Not all components would be applicable for emails, but a brief description will of common ones will still be covered.

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

## Regex Components

### Anchors

Anchors do not match any characters, but rather a position before, after, or between characters. The `^` matches the position before the first character in a string while `$` matches the position right after the last character. There is a way to enable multiline mode, however, it would not be classified as a anchor and will be discussed further in detail later. In a specific case of the expression shown above for email matching, both the `^` and `$` are used to "anchor" a given email.

### Quantifiers

Quantifiers indicate how many instances of characters, groups, or character classes must be present in a given input for a match to be found. There are two `+` given in the email expression, meaning there are a total of three instances that must be provided. The first is the input prior to the `@` symbol and then another prior to the `.` which usually follows with a 'com', 'net, 'org', etc.

### OR Operator

The OR Operator matches characters either left or right of the `|` operator, meaning if a character or instance either side of the operator is found, it is accepted or can be changed for the other. For example, `t|T' would indicate either capitilaztion is accepted or if given the functionality, would replace one for the other. Because emails are cap sensitive and need to be exact, it would not make sense to use an OR Operator when matching an email.

### Character Classes

Character classes are used to distinguish types of characters, usually numbers or letters. `\d` is used in the expression, which specifically matches single characters that is a digit, but only the first digit within a string. This is used to see if the user inputed a digit after the `@` which would deny it as email handlers should not contain any numbers.

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
