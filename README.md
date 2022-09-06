# Regex Tutorial

Hey guys, today I am here to create a tutorial readme on the subject of Regex. As a Junior Developer, or as i like to say, Web Developer in developement, we have to read a whole host of documentation. These can be written by anyone with any level of skill in the corresponding area, and what i find is most important is we keep imparting our knowledge on each other. 

## Summary

Regular Expression, shortened as Regex, is a sequence of characters that specifies a search pattern in text. These search patterns are usually used by string-searching algorithms for 'find' or 'find and replace' operations on strings for input validation. Most general purpose programming languages support the use of Regex either natively or via libraries.

The regex i will be breaking down will be as follows;

`/^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$/g`

This regex has the ability to validate an `email` address.

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

- `^` and `$`<br><br>

- `^` matches the start of the string, eg. `^Hey` would match any string starting with Hey
- `$` matches the end of the string, eg. `there$` would match any string ending with there
- By not providing anchors search anywhere in the text for the string provided<br><br>

My Example;<br>
At the beginning of the regex `/^[\w-\.]` the `^` matches the start of the string while at the end `[\w-]{2,4}$/g` the `$` matches the end of the string.<br><br>

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.

-  `*`, `+`, `?`, and `{}`<br><br>

- `*` will match 0 or more times
- `+` will match 1 or more times
- `?` will match 0 or 1 times
- `{n}` will match exactly `n` times, eg. `{3}` will match 3 times<br><br>

My Example;<br>
There is 3 `+` quantifies in this regex `/^[\w-\.]+@([\w-]+\.)+` all coming after a Grouping Construct of Bracket Expression allowing us to match the groupings `1 or more times`.<br><br>

We can also see at the end of our regex `[\w-]{2,4}$/g` the `{}` allow us to match specifically between the `2` and `4` times of the previous token, allowing us to take in region specific emails such as `hotmail.com` and `hotmail.co.uk`. 
<br><br>

### Grouping Constructs

By wrapping the grouping constructs around a search we can capture only what is defined within the parenthesis and divide our search into groups.

- `()`<br><br>

- `(a-z)` is a group matching lowercase letters<br><br>

My Example;<br>
In the middle of this regex `([\w-]+\.)+` you can see there is one Grouping Construct, this allows us to group multiple tokens together and create a capture group for extracting a substring or using a back reference, such as the `+`.<br><br>

### Bracket Expressions

Bracket expressions are used to define a set of characters that can be matched.

- `[]`<br><br>

- `[abc]` matches any character in the square brackets<br><br>

My Example;<br><br>
In the front 2 thirds of the regex `/^[\w-\.]+@([\w-]+\.)+[\w-]` we can see 3 sets of `[]`, these Bracket Expressions allows us to match any character in the set.<br><br>

### Character Classes

These are characters that represent a class of characters.

- `\d`, `\w`, `\s`, `.` and `\p`<br><br>

- `\d` matches a single character that is a digit
- `\w` matches alphanumeric characters including underscores `_`
- `\s` matches spaces, tabs, and line breaks
- `.` matches any character except line breaks
- `\p` matches a character in the specified unicode category

also

- `[abc]` matches the characters inside the square brackets
- `[^abc]` adding the caret matches any characters NOT in the brackets
- `[0-9]` adding the dash matches characters in that range<br><br>

My Example;<br>
Again in the front 2 thirds of the regex `/^[\w-\.]+@([\w-]+\.)+[\w-]` we can also see 3 sets of `\w`, this allows us to match alpanumeric characters within each expression, including underscores. It is also important to note the `-` special character after the `\w` is also just allowing us to match that special character within the Bracket Expression.<br><br>

### The OR Operator

The OR Operator will search for either the term defined on the left or right.

- `|`<br><br>

- (cats|dogs) will match either cats or dogs, only 1 has to be present to match<br><br>

My Example;<br>
There is no OR operators within this example.<br><br>

### Flags

Flags are optional and have the ability to change how the expression is interpretted.

- `i`, `g`, `m`, `u`, `y` and `s`<br><br>

- `i` will ignore case, making an expression case insensitive
- `g` will retain the index of the of the last match, this allows newer searches to start at the end of the previous match, this way you do not return the same matches.
- `m` when this multiline flag is enabled, the beginning and end anchors, `^` and `$`, will match the start and end of lines, instead of the whole string
- `y` will ignore the global flag if set, `g`, and will match only from its last index position
-`s` will match any character, including new line<br><br>

My Example;<br>
At the end of our regex `$/g` we can see the `g` is present, this allows us to retain the index of the last match, allowing for iterative searches.<br><br>

### Character Escapes

- `\`<br><br>

-  If a special character modifies your regex you have to use `\` to exit what it does as restore the original literal meaning of the character following it.<br><br>

My Example;<br>
In the front half of the regex `/^[\w-\.]+@([\w-]+\.)` we can see 2 character escapes. As we learnt above `.` is a special character that modifies our regex to `match any character except line breaks`. We use the character escape `\` followed by the `.` thus creating `\.` which now just allows us to match the full stop itself, not its Character Class.<br><br>

## Author

Thanks for reading my tutorial. I've dabbled with coding over the last couple of years but really made it a core part of my life recently by undertaking the Coding Bootcamp provided by Trilogy. If you would like to see some more of my work, you can find my github profile [here](https://github.com/Clarky117/).
