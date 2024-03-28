# Title (Regex Tutorial)

## What is a Regex? 
A regex, short for "regular expression," is a sequence of characters that define a particular search pattern. Primarily used for pattern matching within strings, regex is an important tool that allows users to efficiently search, validate, parse, and replace certain patterns of characters within a string spanning over large bodies of text. 

## Summary

In this tutorial, we will be breaking down the components of a Regular Expression used to search for a specific hex value, i.e., hexadecimal numbers. A hexadecimal number is part of a color coding system that labels colors with a hashtag followed by a group of 3 or 6 characters that are unique to that color. (ex: #abc or #abc123).
Below is the regex that I will be explaining in more detail.  

Regex Expression: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/` 


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
Anchors in the context of a regular expression mark the beginning and the end of the expression. In our regex, `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, the beginning is marked by the `^` and the end is marked by the '$'. These anchors are what is called an exact match anchor, which finds a string that matches all of the requirements for each part of the expression. In our case, the string must begin with a '#' and have a combination of three or six total characters that are lowercase letters a-f or numbers 0-9. An exact match will not accept a string that exceeds the character limit set by the quantifiers {6} and {3} within our regex. 

### Quantifiers
Quantifiers are the components of the regex that take a specified amount of characters from a search pattern. In our regex, two quantifiers can be seen inside the curly brackets, `{6}` and `{3}`. Our first quantifier, `[a-f0-9]{6}`, is telling the computer to find a string with six characters that contains lowercase letters a-f or numbers 0-9. Our second quantifier,  `[a-f0-9]{3}`, is telling the computer to find a string with three characters that contains lowercase letters a-f or numbers 0-9. Our final quantifier is the '?' adjacent to the '#' which tells the computer to find a string that contains a single '#' or none at all. 

### OR Operator
The OR Operator in our regex expression is marked by the `|` between our two quantifiers in brackets. This OR Operator servers two purposes. The first is it allows our search to find a string with six characters OR a string with three characters that meet the parameters inside the brackets. The second purpose is capturing and storing strings that meet the parameter requirements for later use. 

### Character Classes
Character classes are components within our regular expression that tell us what type of characters to expect. In our regex, we have two character classes: `[a-f0-9]` and `[a-f0-9]`. 
`a-f` searches for strings with letters between a-f. `0-9` searches for strings containing digits 0-9.

### Flags
The flags for `/^#([a-f0-9]{6}|[a-f0-9]{3})$/` are marked by the `^` and `$`. While they share similar function to anchors, the purpose of the flags `^` and `$` is to increase the amount of matches the computer will find. They accomplish this by telling the computer search for a match at any line that begins with #, avoiding any strings that do not start with # from being returned as a result. 

### Grouping and Capturing
Grouping and Capturing is used in regular expressions to indicate which parts of the strings are to be grouped together and captured. We can identify grouping and capturing in our regular expression by looking at what is inside the parentheses: `([a-f0-9]{6}|[a-f0-9]{3})`. This captures any string that meets the grouping requirements of having three or six characters containing lowercase letters a-f and/or digits between 0 and 9.

Example: `"abc123, efg456"` In this example, the regex is looking for one of two expressions that match the requirements of the search pattern inside the parenthesis. In this case, `abc123` would be accepted first because it's the first string that meets the criteria of having three or six characters containing lowercase letters a-f and/or digits between 0-9.

### Bracket Expressions
In our regular expression, we have two sets of brackets which both contain `[a-f0-9]`. This bracket expression tells the computer to look for a hexadecimal digit based on the two parameters it outlines. The first parameter, `a-f`, searches for any string that has lowercase letters a-f. Our second parameter, `0-9`, searches for any string that has contains numbers 0-9. The string that has these parameters can be any length. 

Example: "abcdefgxyz321" In this string, the lowercase letters that would be chosen are `abcdef` because they are lowercase letters that are between a-f. The second component of the string that will be chosen is the numbers `321` because they are numbers between 0-9.

### Greedy and Lazy Match
In this section I will discuss the difference between a Greedy and Lazy match. A Greedy match tries to match an element as many times as possible, yielding a large number of search results. Conversely, a Lazy match tries to match an element as few times as possible, yielding fewer search results. A Greedy quantifier can be represented by the following characters `*`, `+`, `?`, `{ n }`, `{ n ,}` `{ n, m }` and to turn a Greedy quantifier into a Lazy quantifier we simply add a question mark to it like this: `*?`, `+?`, `??`, `{ n }?`, `{ n ,}?` `{ n, m }?`. Using our regular expression,  `/^#([a-f0-9]{6}|[a-f0-9]{3})$/`, an example of a Greedy match would be `/^#*([a-f0-9]{6}|[a-f0-9]{3})$/` with a Greedy quantifier inserted after the hashtag and before the parentheses. And to turn it into a Lazy match we would add the question mark to our Greedy quantifier so our regex looks like this: `/^#*?([a-f0-9]{6}|[a-f0-9]{3})$/` 

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
