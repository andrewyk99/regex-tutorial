# Regex Tutorial - Matching an Email

This tutorial goes over a brief explanation of of what regex are and specifically the use of regex to match emails using the expression `/^([a-z0-9_\.-]@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. This would be a great way to validate emails when using technologies that allow the use of regex such as JavaScript, Java, C, C++, or Python.

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

Flags are optional that can be attached to regular expressions, either separately or multiple flags together in any order. Some functions flags provides are global searching or case-insensitive searching. Some examples would be `g`, `m`, `i` which do a global search, multiline search, and a case-insensitive search respectively. No flags are used in the email regex. 

### Grouping and Capturing

There are three capturing groups for email matching. The first group is `([a-z0-9_\.-]` which captures the email name prior to the `@` which also is in the regex that separates the email domain which is captured in the second group `([\da-z\.-]+)`. The last group is `([a-z\.]{2,6})` which captures the top level domain, such as `.com`, `.org`, or `.net`. All of the groups are connected with `+`.

### Bracket Expressions

Brackets create a set of characters to match, either to show which characters should match or should not match. The first group in this email regex, `[a-z0-9_\.-]`, matches any letter a-z and is case sensitive. It also matches any numbers and characters `_`, `-`, and `.`. The second group `[\da-z\.-]` also matches any letters and characters `.` and `-`. Remember from the character class the `\d\` matches any single digit as well. The last group contains a bracket expression `[a-z\.]` which again matches any letter and charcters `.`. 

### Greedy and Lazy Match

A "Greedy" match means it matches the longest possible string and a "Lazy" matches the shortest possible string. This email regex contains "Greedy" matches because it as the `+` quantifier, which means it will match as many times until it is given back everything it needs. Another "Greedy" match is the `{}` that is used in the last grouping, which indicates the acceptance character count. Other "Greedy" expressions would the `*` and `?` symbols. The `*` is a repeater symbol and the `?` which tries to match the following character with a given character or replaces any non specified character with nothing.

### Boundaries

Boundaries are similar to anchors in that they are not "consumed" characters, but it shows where a match should occur. The `\b` is how a boundary can be set, for example, `\bcar` would match 'car' in 'carrode' and `car\b` would match 'car' in 'racecar' but not vice-versa. They would also match 'car' by itself. Again, since emails should be standalone, boundaries would not be used in an email match.

### Back-references

Back-references refer to a previous part of the matches regex. Back-references are called with a `\` and a single number. The part the back-references refer to are called "subexpressions". The back-reference always follows after the subexpression. For example, `^(.)(.)(.)\3\2\1$` (the `.` indicates any single character) if the user were to input abc, the regex would reply with 'abccba'. Back-refernces would not be used for email matching.

### Look-ahead and Look-behind

Look-ahead and look-behind, or altogether called look-around, shows the result of the match either match or no match. Like anchors and boundaries, they do not consume characters in a string but only determine if a match is possible or not. `(? ... )` is used to call a look-around. There are standard look-aheads and look-behinds as well as a negative look-ahead and -behind. Neither would be used for email matching.

## Author

Hi! My name is Andrew Kim and I'm a full-stack developer (in training). If you wish to view my projects, you can go to https://github.com/andrewyk99.