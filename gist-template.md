# The Best Regex Tutorial Ever!

This exists to break down what a regex is and how it is used. This is available for anyone to read, and clarify questions on what a regex is, how to use them, and what makes a regex. In short, a regex or regular expression, is a series of characters and symbols used to match strings against a desired format or content.

## Summary
<hr>

In this tutorial I will be describing and explaining a regex to match phone numbers. In todays world, the telephone is a staple of communication. Every user of the internet and software will have a phone number, to validate that a user enters a phone number a phone number regex will ensure users do not enter invalid entries. A phone number regex is a foundational one that is and will continue to be used routinely for years to come.

Examples:
> /^[0-9]{3}\-[0-9]{3}\-[0-9]{4}/

Would match a phone number with a format of 123-456-7890.

> /^\([0-9]{3}\)\-[0-9]{3}\-[0-9]{4}/

Would match a phone number with a format of (123)-456-7890.

> /^\([0-9]{3}\)[0-9]{3}[0-9]{4}/

Would match a phone number with a format of (123)4567890.

>/^[0-9]{10}/

Would match a phone number with a format of 1234567890



## Table of Contents
<hr>

- [Components](#regex-components)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components
<hr>

 A regex when seen by a human can look confusing and make little sense. However when broken down into it's different parts, it becomes much simpler to see the pattern. A regex is always contained by forward slashes '/'. These denote the boundaries of the regex so the computer knows where to start reading the regex and where is ends. Other components include: '.' which will match any single character, '\' which is an escaping character, it is used to escape the regex and instruct the computer to interpret the following character literally, '$' matches any string where the preceeding text is present at the end of a string, '^' matches any string where the following text is present at the beginning of a string, '[]' matches any single character in a range or set within the brackets, '|' indicates an 'or' operator within the regex, lastly '()' is used to group expressions. These components can be used in combination with each other to build the regex you wish. In our case of a phone number, we will need to use brackets & carats.

### Anchors
<hr>

 Some of the components listed earlier are called anchors. Anchors are symbols used to match strings at either the beginning or end of the string. Examples of anchors include the carat and dollar sign. As described earlier, the carat matches a string starting from the beginning. For example: the regex '/^cat/' would return true is compared against the word 'catharsis' since the word catharsis starts with the evaluated expression of 'cat'.

### Quantifiers
<hr>

 Quantifiers are used to dictate the number of characters you wish to match. In the case of a U.S. 10 digit phone number, the pattern we would be seeking to match would be as such: ###-###-####. Where the first two sections require 3 digits, and the last section requires 4 digits. Quantifiers can be acheived a few different ways, however for the purposes of a phone number we will be using x{n}. Where 'x' is the digit to match and 'n' is the number of digits we want. For example "/[0-9]{3}/" would match a series of 3 digits between 0 & 9.

### Grouping Constructs
<hr>

 Grouping constructs is performed by placing an expression within parenthesis. By doing this you can match substrings within the evaluated string and apply quantifiers to the substring. You can also use this to capture substrings for reference later on. Capturing substrings numbers them from left to right, where 0 represents the captured substring and each number afterwards will provide the position of each captured substring within the evaluated string. 

### Bracket Expressions
<hr>

 Bracket expressions allow for evaluations of multiple characters in place or for a range of characters. Bracket expressions use the square brackets '[]' to signify the range of characters for potential matches. One example would be a regex of '/[rfbs]un/' whcih would match against the words 'run', 'fun', 'bun' & 'sun'. However it would not match against 'gun' as the letter 'g' is not contained in the bracket expression. This can also be used to match a range of characters. For our phone number example we would want to check all single digits from 0-9. This would be done by placing [0-9] into our bracket expression. 

### Character Classes
<hr>

 Character classes allow you to match a symbol from a set of characters. Given our phone number example, the digit character class would be most helpful. The digit character class is denoted with '\d', this will match any digit in the regex evaluation. Other character classes include '\s' which will match a whitespace symbol, or '\w' which will match any word character including digits & underscores. 

### The OR Operator
<hr>

 The OR operator is denoted with a single '|'. This logic operator is the same as the OR operator used in JavaScript which is denoted by '||'. This allows for matching against multiple options in the regex. A simple example would be matching '/flower|bush/' against the string 'The flower on the tree is nice'. The regex would match flower since it may match either flower OR bush in the evaluation. It would also return true against the string 'The bush is large'. However it would return false when evaluated against the string 'Deciduous trees lose their leaves each autumn' as neither the values of flower or bush are present in the string. This allows for evaluating expressions for multiple substrings where the desired terms are not always the same.

### Flags
<hr>

 Flags are placed at the end of a regex out side of the closing '/'. These flags allow for things like gloabal searching, case insensitive searching or allowing anchors to match newline characters allowing for multiline searches. The global regex will allow the regex to evaluate multiple matches within the evaluated string. Without the global flag the evaluation would stop at the first instance of the matching regex. 

### Character Escapes
<hr>

 Character escapes are denoted with '\'. Since regex uses various symbols to mean different things, the character escape is used to stop the execution of the function executed by the special character. One example would be the square brackets used in a range. When the computer sees the '[]' it assumes that everythign contained within those brackets is a range of values that it would use to evaluate the string. If however, we want the computer to match literally against a square bracket, we would place a '\' before the bracket. This tells the computer to ignore whatever function it would normally execute and instead macth against that character literally. This would look like: '\['.

## Author
<hr>

Jacob Reeves

https://github.com/JDReeves86