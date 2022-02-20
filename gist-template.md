## Summary
In this gist, I will be covering the Regex below which is confirming that a user has entered a valid email address:
```md
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

I will be describing how this Regex functions by breaking down each part of the expression and describing what it does.

User Story: <br>
AS A web development student <br>
I WANT a tutorial explaining a specific regex <br>
SO THAT I can understand the search pattern the regex defines


## Table of Contents
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)

<br>

## Regex Components
Because a Regex is considered a literal, our search patterns must be wrapped in slashes / /. Our example uses literal notation, determined by the slash at the beginning and end of the Regex, to create our search pattern: <br>
```md
--> /   ^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$     / <--
```

<br>

## Anchors
The anchors for Regex are a caret ^ and the dollar sign \$. <br> 
The caret ^ after the inital slash / is letting us know that the string we are looking for begins with the characters following the caret ^. In this example, we are looking for a range of possible matches which are displayed in our bracket expressions. <br>
```md
/ --> ^  ([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

<br>

Additionally, our pattern ends with a dollar sign \$ before the final slash /. This tells our search pattern that our string needs to end with the characters listed before the dollar sign \$. For our example, that would be any lowercase letter or a period. <br>
```md
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$ <--   /
```

<br>

## Quantifiers
Quantifiers sets limits of how many times the preceeding pattern can be matched. The quantifiers in our example contain two numbers separated by a comma within a set of curly brackets:

```md
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]    --> {2,6} <--    )$/
```

Our first digit, 2, is the minimum number of letters our string can be. <br>
Our digit to the right of the comma sets our maximum of 6 letters.

Additionally, two of our sets in parentheses () include a plus symbol +. The plus symbol + is a quantifier that states the prior pattern in the square brackets could occur one or more times.

```md
/^([a-z0-9_\.-]+ <--    )@([\da-z\.-]+ <--    )\.([a-z\.]{2,6})$/
```

<br>

## Bracket Expressions
Bracket expressions are patterns that outline the character we want to match. <br>
Our example contains 3 sets of bracket expressions, lets break down what each set is looking for: <br>
```md
[a-z0-9_\.-]
```
: any lowercase letters between a and z, any number between 0 and 9, can include underscore _ or hyphen - or period . <br>
```md
[\da-z\.-]
```
: \d is another way of saying any number between 0 and 9, any lowercase letters between a and z, can contain a hyphen - or a period . <br>
```md
[a-z\.]
```
: can be any lowercase letter and include a period .

<br>

## Character Classes
In Regex, character classes define a set of characters, any of which can occur in an input string to fulfill a match. Our example utilizes the character class \d in our second set of square brackets. The \d character class matches any Arabic numeral digit, meaning it is the equivilant of using 0-9 as we did in our first set of square brackets.

```md
/^([a-z0-9_\.-]+)@([\d <--    a-z\.-]+)\.([a-z\.]{2,6})$/
```
<br>

## Character Escapes
Some characters have special meaning in Regex and a character escape allows us to insert one of the characters that would otherwise be interpreted literally. 
Our example uses character escapes to include periods . multiple times. Because a period . has special meaning in Regex, we need to add a backslash \ so the period . doesn't get interpreted literally. 

```md
/^([a-z0-9_  \. <--    -]+)@([\da-z  \. <--    -]+)  \. <--    ([a-z \. <--    ]{2,6})$/
```


## Author
Megan McLean, current student at the University of Washington's Web Development Bootcamp | https://github.com/425megs