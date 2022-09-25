# RegEx Tutorial

This tutorial will serve as a crash-course in how to utilize RegEx, otherwise known as Regular Expression. As denoted in the name RegEx uses various Expressions to find specific patterns of characters that are in any given string, or in order to replace one or more characters with something else in any given string. The following breakdown will explain how these Regular Expressions as the parameters of how we will search for, as well as validate data.

## Summary

Example --> The following regular expression can be used to verify that user input is a valid email address. This tutorial will serve to breakdown the contents of the snippet below in order to explain exactly how it works to find and validate data.

Snippet:  `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors
Characters that are within a Regular Expression that target as well as denote the beginning and end of a set of strings are called Anchors. For instance, the `^` character in the above example will match the beginning of the target string, while the `$` will match the end of the target sting. To further explain the functionality of these anchors, say we took 2 different emails, `name@email.com` and `name@email.coooooom` and tried to validate them using the above Regular Expression (`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`), only `name@email.com` would be validated since it is within the given parameters or `quantifiers` in the expression.

### Quantifiers
As explained above, `name@email.coooooom` will not be validated because it did not fully satisfy or match the quantifiers in the given expression. If we look at this expression closely, we can see that these are not a randomly allocated group of characters, but that each one will gives certain instructions for what is required when searching and validating a given string. For instance, the expression `{2,6}` is a `quantifier`that tells the expression that says that the section after the period must be between 2 and 6 characters in order to validate. Looking at the email that will not validate, is is clear to see that `.coooooom` has 8 characters and is therefore not accepted by the quantifier.

### Character Classes
The email match expression example happens to have a `character class` of `/d`, which acts as known as the `digit character class`. For example, in the section `[\da-z\.-]`, it will find any single digit as well as characters `a-z`.

### Grouping and Capturing
When we are required to return certain sets of data, we utilize `Groups`. In our email validator, there are 3 parts that are called by RegEx:

- Username: `([a-z0-9_\.-]+)`
- Domain: `@([\da-z\.-]+)`
- Extension: `.([a-z\.]{2,6})`

Each one of these parts are their own `Group` and are `captured` together in order to make a string.

### Bracket Expressions
If we take a closer looks at the `Groups` mentioned above, we can see that `Bracket Expressions` can be found. So if we look at the `username` portion of the example RegEx above, `([a-z0-9_\.-]+)` contains the bracket expression: `[a-z0-9_\.-]`.

Expressions like this are used to locate matching or invalid sets of data like letters, special characters or numbers.

For Example: `a-z` is searching the string for lower-cased letters. `0-9` searches for digits. `_` searches for specifically underscores and `\.` is searching for periods in the string. This `\` is required to find a period because it needs to be found and `captured`. This is know as `escaping` a character and making it into a `literal`.

### Greedy and Lazy Match
Inside this particular example we can see that its groups are using a `Greedy Match` method. This is denoted by the `+` symbol, and allows the expression to discover the largest possible match. This can be veiwed as yet another quantifier. In the `extention` group we can see that instead of `+` it  is using `{2,6}`.

## Author

Taha is a Full Stack Web Developer who is expanding his skills on coding through practice and resources.Checkout his github at: [github link]() 
