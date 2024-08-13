# Regex Tutorial Gist: Matching an Email
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
Grouping contructs are represented by parentheses () and are meant to allow for search of subexpressions by indicating which sections of the expression should be treated as a single unit. In our email example, there are several instances of searchign for letter expressions, but by having them separated into different parenthetical statements, it specifies which sections are unique. It searches for letter characters both in the beginning of the email address before the @ as well as prior to the . and also following it. Each section has different parameters (such as attaching a quantifier to the ending snippet or allowing for uppercase or special symbol characters in the other snippets. It functions similar to the parentheses in mathematical statements, which indicates the treat the contents as their own content separated to the preceding and following items. Another real-life example would be in the case of a phone number search `(\d{3})-(\d{3})-(\d{4})` which specifies the treat the digits as 3 separate groupings with specific quantifiers attached.

### Bracket Expressions
Bracket expressions (or positive character groups) refer to a specific range of characters occurring within a set of brackets [] that are meant to be matched against. This will allow for more customized ans specific searches versus general patters. Of note, using a hypen between characters can be used to more succinctly represent a range. For instance, `[abcdefg]` can be represented as `[a-g]` or `[5678]` could be represented as `[5-8]`. The above email matching example uses bracket expressions to show it allows to any letter within the range of a-z and any number/digit within the range of 0-9. Something to note is if a carat occurs WITHIN brackets, such as `[^0-5]`, it would match anything except the included characters (ie: allows for digits 6-9 only in this case).

### Character Classes
A character clause is used when you want to specify a specific string/set of characters to be included in the match. Examples of character classes are ".", which represents any character (other than the \n used to represent a new line to begin) or the "\s" which represents a space. `\d` is another way of writing `[0-9]` and will match for any numerical digit between these values. `/w` is another way to write `A-Za-z0-9_]` and will match to upper or lowercase letters as well as underscore symbols. Of note, the character classes can be capitalized (for example `\W` in order to reference the OPPOSITE of the character class. This would accept anything OTHER than letters or underscores.

### The OR Operator
The OR operator (seen as ||) represents some acceptable pattern which has more than one option. This is not seen in the email Regex, but an example would be searching for phone numbers. The pattern as follows `/^(()?\d{3}())?(-|\s)?\d{3}(-|\s)\d{4}$/` contains several instances of the snippet `(-|\s)`. When searching for a phone number, the operator serves to accept either the dash/hyphen OR a space. This would accept '123-456-7890' OR '123 456 7890' as matches, but would not accept anything else like '123&456&7890'. This operator COULD be used in an email search if customizing to say only accept .edu or .org addressed which would look like `\.(edu|org)`. 

### Flags
If a flag occurs in with a regex (they are optional), it will add certain functionality to the search. Some examples of flags are: i (makes the pattern case-insensitive) or g (allows for the search to match multiple instances of the pattern rather than just the first occurrence of the pattern).  Using the following flag `/^[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}$/i` would accept techthings@gmail.com and would also accept TECHTHINGS@gmail.com and would even accept TechThiNGs@gmail.com as matches. Attaching the g flag would mean all these would be identified as matches if in the same document. Another example of flags are m (multiline - will match the beginning and the end of a string as multi-line and only affects the anchor characters). Others are u (unicode- allows for enabling of Unicode support like withe emojis) and s (dotall - allows to match with newline \n characters as well, which is not allowed by the normal expression.

### Character Escapes
In regex, the backslash `\` character is meant as a separator to indicate a type of parameter/grouping/class from a literal character. For example, in the email match regex, the snippet `([\da-z\.-]+)` includes the escape with \d to indicate the search for a digit character instead of the literal character d. This escape symbol will come before many of the character classes, but is negated if it is found within a set of brackets. 

## Author
My name is Erin DeVine and I am student in the full-stack web development bootcamp through University of Richmond. Above details my findings when researching REGEX.
Check out my GitHub: https://github.com/erindevine0229 or email me at erinj291@gmail.com with any questions!
