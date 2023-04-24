# The Colorful World Of REG(HEX)EX 🎨

The purpose of this tutorial document is to allow anybody who reads to to understadn the inner workings of a REGEX Expression to match a Hex Value of any given color, so long as it matches the REGEX Expression used to find any string of characters! Take a dive into the tutorial to learn the secrets behind the Colorful World of REG(HEX)EX!! 🎨

## Summary

The general REGEX Expression that is used to match many or even one strings of a HEX Value is as follows:
`/^#?([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$/`
Which can be used in languages such as CSS and Javascript alike! 

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

Taking a look at our REGEX for our HEX values above `^` and `$` are considered anchors.
Anchors can be used to are used to match positions of specific characters in a string.

 * `^` is used to match the start of a string.

 * `$` is used to match the ending of a string.

### Quantifiers

Quantifiers can be used to limit or specify the amount of characters can be matched. 
An example of this can be seen in our REGEX Expression `[A-Fa-f0-9]{6}`.
Now lets break this down further:

 * Our Quantifier `{6}` is what specifies a group of characters matched `[A-Fa-f0-9]` MUST be matched exactly six times in our HEX value.

 * `{}` Can be used up to three different ways to limit characters matched in our case `{n}` makes a pattern match exactly `"n"` times
    just like in our above bulletpoint `"n"` is represented by the numebr you put in the curly brackets.

 * Building on the concept of quantifiers you can also do `[A-Fa-f0-9]{3}` this mean that a group of characters within a HEX value can also be  matched to exactly three characters in the value.

 * You can also have both of the Quantifiers together in the same expression like so `[A-Fa-f0-9]{6}|[A-Fa-f0-9]{3}`. So our regex expression will return a HEX value that is matched exactly `{6}` times AND exactly `{3}` times as long as it contains characters that are either uppercase or lowercase with characters using `[A-F] and [a-f]` and numbers `[0-9]`.

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
