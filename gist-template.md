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

    Our HEX Value REGEX:   `/^#?([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$/`
      
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

Group Constructs are able to be used to group parts of our REGEX expression together, this means that this group is treated as a single pattern.

 * In our expression we group `([A-Fa-F0-9]{6}|([A-Fa-f0-9]{3})` together. Doing so creates two possible patterns for our HEX Values

 * Our two possible patterns for our HEX Values can the be returned as Six Hexodecimal Characters OR Three Hexodecimal Character for a HEX Value.

### Bracket Expressions

Bracket Expression can be used to match a range of characters that are inside a set of open and closed brackets `[]`.

 * In our case for a Hex Value the bracket expression for us contains a set range of characters `[A-Fa-f]` and a set range of numbers `[0-9]`

 * Thus makes our full bracket expression to contain a set of characters and numbers that range from `[A-Fa-f0-9]` this will match us with any
   uppercase, lowercase, hexadecimal character and digit.

 * You can set the range of characters for the whole alphabet as well such as `[A-Za-z]` which can use in other methods such as matching usernames, emails or passwords.

### Character Classes

Character Classes can be used to match for specific sets of characters

 * For one example we've already been using a Character Class with our HEX Value REGEX Expression which is `[A-Fa-f]`. This character class tells our REGEX to look for any characters if
  they are uppercase or lowercase within the range of characters set. In this case it'll search for characters that are with in the range of `A-F and a-f`.

 * Other Examples of character classes cand be `[abc]` which will search for any of the included characters, as long as a word contains the letters `a, b, and c` it will return word containing those set letters. Where as `[^abc]` will exclude all of the contained characters.

 * `\w` will search for any word character that is alphanumeric and underscored.

 * `\d` will search for any digit `[0-9]` which could possibly be usefull in shortening up our REGEX Expression for our HEX values.

 * `\s` shall search for any whitespaces in a search. This would mostly search for spaces, tabs, or line breaks.

 * These are some examples of class selectors. But in our case for a HEX Value REGEX Expression like ours the main Character Class that we are using in ours is `[A-Fa-f]` as mentioned in our first bulletpoint of the Character Classes section.

### The OR Operator

The OR Operator used to specify to look for alternative patterns in our expression. Think of it as a way to tell your expression to look for `"A pattern like this OR A pattern like that"`.

 * The OR Operator is used by having `|` placed within your expression.

 * Take a look at this section of our REGEX Expression `([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})` Where would the OR operator be in this expression and what would it translate to?

 * The OR `|` Operator in our Expression tranlates to telling our Expression to look for any patters that contain the 6 `OR` 3 hexadecimal characters `A-Fa-f` and `0-9`.

 * A simple way to remember the OR Operator to remeber `This OR That`.

### Flags

Flags can be used an several ways to modify how a REGEX Pattern can be matched. For Example:

 * `i` is a flag that allows the REGEX for the search to be case-insensitive, meaning no difference between uppercase and lower case characters.

 * `g` Would search for all matches globally. Without it you would get just the first instance. i.e you could search globally for all instances of the word `color` in a document; The `g` flag would then highlight or select all of the instances the word `color` occours on within a document, and without the `g` flag it you would only get a return of the first instance of the word `color`.

 * These are just two of the six examples of flags avaiable in javascript and how they can be used to tailor a regex expression suitable to your needs.

 * However in our own REGEX Expression there are no flags beeing used.

### Character Escapes

Character Escapes is a feature within REGEX that cann allow you to pinpoint special characters. This allows you to match characters that would be considered metacharacters with special meaning to be matched in a literal sense instead.

 * `\.` Can be used to match a period in a literal sense. Whereas `.` would be used to match ANY character instead.

 * `\[` Is used to match a literal opening bracket. `[` would be used to start a character class instead.

 * `\(` Would be used to search a literal opening parnthesis. `\(` could be used to start a group.

 * There are a few other character escapes that can be used for countless REGEX Expression. However Just like Flags in our case none are being used for our HEX Value REGEX Expression.

 ### HEX Value REGEX Example

 vvv-- A Simple yet Easy example to help showcase if a HEX Value would be Valid with our REGEX Expression can look like this --vvv

      const regexHexValid = /^#?([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$/;

      console.log(regexHexValid.test(#8686b0));
      //true
      console.log(regexHexValid.test(8c6));
      //true
      console.log(regexHexValid.test(#432a56));
      //true
      console.log(regexHexValid.test(#c08));
      //true
      console.log(regexHexValid.test(90b0b4));
      //true
      console.log(regexHexValid.test(g699Z));
      //false

Now if we look at our `const regexHexValid = /^#?([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$/;` we can break this up one step at a time and explain why the first 5 hex values are `true` while the last one is logged as `false`.

 * We've already covered in our first section [Anchors](#anchors) where `^` and `$` are used to match the start and end of the string.

 * Second, if you look you'll see we have `#?` this part of the expression is used to match an optional hash symbol at the beginning of our string. Notice how in some of our console logs our HEX Values dont have any `#` symbols at the start of them, but they still passed true? Thats because its an optional condition to our REGEX Expression. If a HEX Value does not contain a `#` it will still reconize it as a HEX Value.

 * Finally, we look at `([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})` in our expression. Our first five `console.logs` return `true`  because the fits all of the five other requrements which is [Quantifiers](#quantifiers), [Grouping Constructs](#grouping-constructs), [Bracket Expressions](#bracket-expressions), [Character Classes](#character-classes), and [The OR Operator](#the-or-operator). This is because the first five HEX values are Hexidecimal values that contain Hexidecimal characters that are `[A-Fa-f]` and contain digits `[0-9]` and are either `{6}` OR (`|`) `{3}` characters long.

 * Why did the sixth and final `console.log` return as `false`? Thats because it is `5` characters long and contains the a letter `g` and `Z` in the value. Which does not fit our REGEX HEX Value expression `/^#?([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$/`.

 * Thank you for reading my REGEX Tutorial and hope this is able to help give you as the read a better grasp on understanding how a REGEX Expression can be used to validate a HEX Value with Hexadecimal characters and Numbers! Not only can you use the information you learned here for HEX Values, you could take what you learned in this tutorial and also learn to use REGEX to match things such as Username, Emails, and Passwords!

## Author

I'm currently a beginner in learning coding, who is currently enrolled in a Full-Stack Web Development Coding Bootcamp! I hope to learn as much as I can as I continue to expand my new knowledge on Web Development and hope to eventually make a career shift into the Web Development career feild! 

[Github Reposetories](https://github.com/MacaroniKetchup?tab=repositories)

You can also checkout my [Portfolio](https://macaroniketchup.github.io/My-Portfolio/) to view some of the projects I've worked on in my bootcamp!

    HAPPY CODING
![Anime Hacker](./image/anime-hacking.gif)