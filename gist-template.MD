# Title (Regex Tutorial)

Introductory paragraph (replace this with your text)

## Summary

## What is a Regex? 
A regex, short for "regular expression," is a sequence of characters that define a particular search pattern. Primarily used for pattern matching within strings, regex is an important tool that allows users to efficiently search, validate, parse, and replace certain patterns of characters within a string spanning over large bodies of text. 

In this tutorial, we will be breaking down the components of a Regular Expression used to search for a specific hex value, i.e., hexadecimal numbers. A hexadecimal number is part of a color coding system that labels colors with a hashtag followed by a group of 3 or 6 characters that are unique to that color. (ex: #abc or #abc123).
Below is the regex that I will be explaining in more detail.  

Regex Expression: /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ 


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
Anchors in the context of a regular expression mark the beginning and the end of the expression. In our regex, /^#?([a-f0-9]{6}|[a-f0-9]{3})$/, the beginning is marked by the '^' and the end is marked by the '$'. These anchors are what is called an exact match anchor, which finds a string that matches all of the requirements for each part of the expression. In our case, the string must begin with a '#' and have a combination of three or six total characters that are lowercase letters a-f or numbers 0-9. An exact match will not accept a string that exceeds the character limit set by the quantifiers {6} and {3} within our regex. 

### Quantifiers
Quantifiers are the components of the regex that take a specified amount of characters from a search pattern. In our regex, two quantifiers can be seen inside the curly brackets, {6} and {3}. Our first quantifier, [a-f0-9]{6}, is telling the computer to find a string with six characters that contains lowercase letters a-f or numbers 0-9. Our second quantifier, [a-f0-9]{3}, is telling the computer to find a string with three characters that contains lowercase letters a-f or numbers 0-9. Our final quantifier is the '?' adjacent to the '#' which tells the computer to find a string that contains a single '#' or none at all. 

### OR Operator
The OR Operator in our regex expression is marked by the | between our two quantifiers in brackets. This OR Operator servers two purposes. The first is it allows our search to find a string with six characters OR a string with three characters that meet the parameters inside the brackets. The second purpose is capturing and storing strings that meet the parameter requirements for later use. 

### Character Classes
Character classes are components within our regular expression that tell us what type of characters to expect. In our example, we have two character classes: [a-f0-9] and [a-f0-9]. 'a-f' searches for strings with letters a-f. '0-9' searches for strings containing digits 0-9.

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
