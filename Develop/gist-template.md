# Regex Tutorial: Matching an Email
Regex, otherwise known as regular expressions, refers to defined patterns of characters which are used to search for specific type of patterns in data or user input. For example, there is REGEX to search for pattens identifying hexidecimal codes (for colors), usernames, emails, URLs and more. An example of use case is searching a  text document for emails or phone numbers of employees.

## Summary
In this tutorial, we will explore how regex expressions are used to identify content/data which follows the pattern identifying email addresses. 
The REGEX explored is as follows: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Looking at the above expression, the first section begins by allowing for any set of characters (lowercase letters, numbers 0-9 or symbols including a backslash, period or hyphen/dash symbol). Following this arbitrary set of characters, there will specifically be an @ symbol to signify the email address domain is to follow. Following the @ symbol, the next characters must be letters only. Next will appear a period (must be this exactly) and then must be only letters (minimum 2 and maximum 6 characters). This will allow for patterns such as .net, .com, .edu, .in and others.

## Table of Contents
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

Character Escapes


## Regex Components

### Anchors
Anchors are two specific symbols which signify the beginning and end of a REGEX expression. The beginning anchor is the carat (^) and the ending anchor is the dollar sign ($). The anchors occur on either side of the string of characters which will be compared against when looking for a match to the expression. In the email example, you can see the anchors `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` of ^ and $ to specify the extent of the expression to be searched for.

### Quantifiers
Quantifiers are ways to limit search results to certain numerical parameters. For example, at the end of the find an email REGEX, the characters allowed is followed by the quantifier of `{2-6}` seen fully as `([a-z\.]{2,6})`. This means the characters allowed must be at least 2 and at most 6. This is meant to limit possible acceptable results to those which are appropriate. For example, a domain extension (like .com .io or .net) should only ever be between 2 and 6 characters.

### Grouping Constructs

### Bracket Expressions

### Character Classes
A character clause is used when you want to specify a specific string/set of characters to be included in the match. Examples of character classes are ".", which represents any character (other than the \n used to represent a new line to begin) or the "\s" which represents a space. `\d` is another way of writing `[0-9]` and will match for any numerical digit between these values. `/w` is another way to write `A-Za-z0-9_]` and will match to upper or lowercase letters as well as underscore symbols. Of note, the character classes can be capitalized (for example `\W` in order to reference the OPPOSITE of the character class. This would accept anything OTHER than letters or underscores.

### The OR Operator
The OR operator (seen as ||) represents some acceptable pattern which has more than one option. This is not seen in the email Regex, but an example would be searching for phone numbers. The pattern as follows `/^(()?\d{3}())?(-|\s)?\d{3}(-|\s)\d{4}$/` contains several instances of the snippet `(-|\s)`. When searching for a phone number, the operator serves to accept either the dash/hyphen OR a space. This would accept '123-456-7890' OR '123 456 7890' as matches, but would not accept anything else like '123&456&7890'. This operator COULD be used in an email search if customizing to say only accept .edu or .org addressed which would look like `\.(edu|org)`. 

### Flags
If a flag occurs in with a regex (they are optional), it will add certain functionality to the search. Some examples of flags are: 

### Character Escapes
In regex, the backslash `\` character is meant as a separator to indicate where 

## Author
My name is Erin DeVine and I am student in the full-stack web development bootcamp through University of Richmond. Above details my findings when researching REGEX.
Check out my GitHub: https://github.com/erindevine0229.
