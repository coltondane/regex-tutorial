# regex-tutorial

This a quick summary of a simple regular expression format that can be used during programming to validate credit card number format.

## Summary

The following regular expression is one that might be used by websites like amazon that have to validate a user entered credit card number to pay for their products. This particular example includes the patterns for Visa, Master Card, American Express, Diners Club, and Discover cards. The following sections will contain a brief explanation of each aspect of the regex, as well as the regex itself. 

^(?:4[0-9]{15}|5[1-5][0-9]{14}|6(?:011|5[0-9]{2})[0-9]{12}|3[47][0-9]{13}|3(?:0[0-5]|[68][0-9])?[0-9]{11})$


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

('^' and '$') - represent the start and end of the regex respectively

### Quantifiers

This regex's quantifiers all match the number of digits required for each card format, the ('5[1-5][0-9]{14}') section of the regex for example matches MasterCard numbers. This format starts with a '5', followed by a digit between '1' and '5', and then {14} more digits. The '{14}' aspect of this snippet is considered the 'quantifier'.

### OR Operator

The 'OR' operator is represented by the '|' character. This is displayed multiple times as it separates the different card types. A snippet of the regex above typed out in english, highlighting the OR (|) operator would read as follows. "Matching Visa Card(OR|) Master Card(OR|) Discover Card"

### Character Classes

Character classes are demonstrated in the regex in the sections represented by square brackets []. Examples include [0-9] meaning any digit ranging from 0 to 9. Or [68], meaning either 6 or an 8 must match there.

### Flags

This regex does not have any flags so it operates under the 'default' behavior. The following characters 'i,g,m,s,u,y' are the only flags used in regular expressions (https://javascript.info/regexp-introduction). The most common flags being (i)case-insensitivity, (g)global matching, (m)multiline matching. 

### Grouping and Capturing

This regex makes use of the non-capturing operator represented by the characters (?:). Anything after those represents the pattern that the string will be checked against, and not saved for later usage. In other words, the regex validates, and the program moves on not using that string again. If there was no '?:' in the parenthesis, then the matching string would be captured for later use.

### Bracket Expressions

In this regex the bracket expressions are the same as the character classes, which can be referenced above.

### Greedy and Lazy Match

In the regex listed above there is not an example of a lazy match, the '{n}' notation however is a good example of a greedy match that is used multiple times. The characteristic that qualifies that syntax as 'greedy' is that it tries to match as many digits as possible because credit cards have a very fixed pattern. A lazy match appraoch would not be applicable here as Visa cards, for example, do not have varying numerical patterns. 

### Boundaries

In the regex used in this example the only examples of boundaries are the start(^) and end ($) symbols. There are however boundaries for strings formatted: (/Astring/Z) and words: (/bexample/b)

### Back-references

There is no example of a back-reference in this regex as the non-capturing method is used. However, if we wanted to capture the card number and reference it later in the regex again, the '/1' notation would be used to make a call to the previously captured value.

### Look-ahead and Look-behind

There is not an example in the above regex of this property, the purpose of these methods is for asserting that a specific pattern will be before or after the specified position. An example where this would be useful would be in URL authentication. making sure that www. precedes a given string, or making sure that .com comes after a given string.

## Author

[Github](https://github.com/coltondane)

