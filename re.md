
# Usage
 - re.search("123", "toto123") : return a truthy match object giving the first occurence, None otherwise


# Patterns expressions
 - any single character except newline : `.`
 - zero or more repetition : `*`
 - one or more repetition : `+`
 - zero or one repetition : `?`
 - explicit number of repetition : `{}`
 - specify a character class : `[abc]`
 - alternation : `|`
 - create a group : `()`
 - create a named group : `<>`
 - complement a character class (if first in the class) : `^` (`[^0-9]` matches any non numerical character)
 - specify the start of the string position : `^`
 - specify the start of the string position : `\A`
 - specify the end of the string positin : `\Z`
 - escape a metacharacter : `\`
 - word character : `\w`
 - non word character : `\W`
 - digit character : `\d`
 - non digit character : `\D`
 - white space or newline : `s`
 - non whithe space or newline : `\S`


# Usefull Pattern
 - single decimal digit : `[0-9]`
 - any non numerical character : `[^0-9]`
 - characters a to z : `[a-z]`
 - hexadecimal characters : `[0-9a-fA-F]`
 - wildcard : `t.ta` matches `tota`and `tata`
 - word character : `\w` equivalent to `[a-zA-Z0-9_]`
 - non word character : `\W` equivalent to `[^a-zA-Z0-9_]`
 - digit character : `\d`  equivalent to `[0-9]`
 - non digit character : `\D` equivalent to `[^0-9]`
 - match a single backslash : use `'\\\\'` or `r'\\'`
 - start of the string : `^foo` or `\Afoo` matches `foobar` but not `barfoo`
 - end of the string : `foo\Z`matches `barfoo` but not `foobar`


# Examples
 - `1.3` matches`123`
 - `abc[def]` matches `abcd`, `abce` and `abcf`
 - `[-abc]`equivalent to `[abc-]`equivalent to `[ab\-c]`
 - `[)*+|]` any of the special characters
 - `t.ta` matches `tota`and `tata`
 - `[\d\w\s]` any digit, word or whitespace character
 - `\.` matches a point "."
 

# Without regex
 - contains : `"123" in "12345"`
 - index : `"toto12345".find("23")`
 - find : `"toto12345".index("23")`


# Ressources 
- https://realpython.com/regex-python/
