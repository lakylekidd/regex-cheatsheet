# Regular Expressions

## Literal Matches
With literal match we use the exact string we would like to search for. e.g. 'cat dog' will match 'cat dog' and not 'cat bird'.
We can also do literal matches to special characters such as a dash '-'. In order to do that we should use a backslash before the special character such as: `\-` which will turn the dash as a literal.
> We can also use the dash at the end of the character class to make it literal : `[a-z-]`

## Character Classes
We can use brakets to match characters included inside of them: `[aeiou]` will match only characters within the brakets. 
We can also use ranges 
- `[a-z]` : will match all characters from a to z lowercase
- `[a-zA-G]` : will match all lowercase characters from a to z and all uppercase characters from A to G.
- `[2-7]` : will match all numbers from 2 to 7
- `[0-9a-zA-Z]` : will match all numbers and all characters lower or upper case.

**Negating Matches**
Negating matches will match whatever is not. e.g:
- `[^a-z]` : will match everything else except lowercase a to z

> We can also match against any character, for example taking the ASCII table, we can match from the 'space' character to the 'tilda' character like so: `[\ -~]`. Notice the space after the backslash which turns the space into literal, then the dash and then the tilda.

## Alterations
Alterations are trying to match whatever is on the left of the pipe `|` and if it doesn't find anything it tries to match whatever's on the right.
We can use alterations like so: `cat|dog|fish|bird` and can be chained.

## Metacharacters
Some metacharacters require backslashes behind them in order to give them special meaning. While other me require backslash to give them the literal meaning.
- the `.` : matches anything except a new line. We need to use `\.` to literally match a dot (.) in the string.
- the `\w` : it's a shortcut of `[a-zA-Z0-9]`
- the `\W` : it's a shortcut of the above but negated `[^a-zA-Z0-9]`
- the `\d` : is a shortcut of `[0-9]`
- the `\D` : is a shortcut of `[^0-9]`
- the `\t` : represents 'tabs'
- the `\n` : represents new lines or line breaks.
- the `\s` : matches any kind of space, such as new lines, line breaks, space, tabs etc.
- the `\S` : same as above in reverse (negated)
- the `\ ` : matches a space


## Quantifiers
The ability to match multiple things at once.
- `*` : 0 or more times
- `+` : 1 or more times
- `?` : non-greedy match. Matching the least matches of possible results against the most. Quantifiers are greedy by nature, meaning they will attempt to consume as much as they can in one go.

**Non-Greedy Example**:
`https?://.*` will make the 's' after 'http' optional.
