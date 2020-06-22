
# Usage
 - `m = re.search("123", "toto123")` : return a truthy match object giving the first occurence, None otherwise
 - `m.groups()`: returns a tuple of matched groups
 - `m.group(0)`: returns the entire regex match
 - `m.group(n)` : returns the nth element of the tuple matched group
 - `m.group(3,2,1)`: returns the matched groups in specified order
 - `m.group('w1')`: returns matched group named 'w1'


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
 - start or end of a word : `\b`
 - non-word-boundary : `\B`
 - non-greedy operators : `?`
 - specify number of repetitions : `{m}`
 - specify numbers of repetitions : `{m,n}`
 - non-greedy set of reps : `{m,n}?`
 - grouping : `(regex)`
 - grouping with quantifier : `(regex)?`
 - backreference to the first matched : `\1`
 - backreference to the nth matched : `\n`
 - named captured group : `(?P<name><regex>)`
 - backreference using named group : `(?P=<name>)` or `(?P=name)`
 - non-capturing group : `(?:<regex>)`
 - conditional matching : `(?(<n>)<yes-regex>|<no-regex>)`or  `(?(<name>)<yes-regex>|<no-regex>)`
 - numbered conditional matching : `(?(<n>)<yes-regex>|<no-regex>)`
 - named conditional matching : `(?(<name>)<yes-regex>|<no-regex>)`
 - look ahead : `(?=<lookahead_regex>)`
 - negative look ahead : `(?!<lookahead_regex>)`
 - look behind : `(?<=<lookbehind_regex>)`
 - negative look behind : `(?<!<lookbehind_regex>)`
 - comment : `(?#...)`
 - alternation : `foo|bar|baz` (tested from left to right)
 - set or remove flag on capturing group : `(?<set_flags>-<remove_flags>:<regex>)`
 
 
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
 - word : `\bbar\b` matches `foo bar baz`, `foo(bar)baz` but not `foobarbaz`
 - non-word-boundary : `\Btoto\B` matches `atotoa` but not `toto`
 - zero or more dash : `-*`
 - one or more dash : `-+`
 - zero or one dash : `-?`
 - any number of characters : `.*`
 - 5 dashes : `-{5}`
 - 2 to 5 dashes : `-{2,5}`
 - 0 to n dashes : `-{,n}`
 - m to infinty dashes : `-{m,}`
 - non-greedy, matches the shortest : `{3,5}?
 - grouping : `(bar)`, same as `bar`
 - quantified grouping : `(bar)*` matches `barbar`

# Examples
 - `1.3` matches`123`
 - `abc[def]` matches `abcd`, `abce` and `abcf`
 - `[-abc]`equivalent to `[abc-]`equivalent to `[ab\-c]`
 - `[)*+|]` any of the special characters
 - `t.ta` matches `tota`and `tata`
 - `[\d\w\s]` any digit, word or whitespace character
 - `\.` matches a point "."
 - greedy vs non-greedy : `<.*>` matches `<foo> <bar> <toto>` in `<foo> <bar> <toto>`
 - greedy vs non-greedy : `<.*?>` matches only `<foo>` in `<foo> <bar> <toto>`
 - `(ba[rz]){2,4}(qux)?` matches 2 to 4 occurrences of either 'bar' or 'baz', optionally followed by 'qux'
 - `(foo(bar)?)+(\d\d\d)?` : at least one occurrence of 'foo' optionally followed by 'bar', all optionally followed by three decimal digit characters.
 - backreference : `'(\w+),\1'`matches `'foo,foo'`but not `'foo,qux'`
 - named groups : `(?P<w1>\w+),(?P<w2>\w+),(?P<w3>\w+)` same as `(\w+),(\w+),(\w+)` but with names for groups
 - `(\w+),\1`same as using named-backrefence `?P<word>\w+),(?P=word)`
 - numbered conditional matching : `r'^(###)?foo(?(1)bar|baz)'` : `^(###)?` indicates that the search string optionally begins with `'###'`. If it does, then the grouping parentheses around `###` will create a group numbered 1. Otherwise, no such group will exist. The next portion, `foo`, literally matches the string `'foo'`. Lastly, `(?(1)bar|baz)` matches against `'bar'` if group 1 exists and `'baz'` if it doesn’t.
 - named conditional matching : `(?P<ch>\W)?foo(?(ch)(?P=ch)|)`  : `(?P<ch>\W)` A single non-word character, captured in a group named ch `(?P<ch>\W)?` Zero or one occurrences of the above `foo` The literal string 'foo', `(?(ch)(?P=ch)|)` The contents of the group named ch if it exists, or the empty string if it doesn’t
 - look ahead : doesn't consume the following chars : `foo(?=[a-z])`in `foobar` matches `foo`, not `foob`
 - alternation : `(foo|bar|baz)+', 'barbazfoo')` matches `barbazfoo`


# Flags
To use as : `re.search('^bar', 'FOO\nBAR\nBAZ', re.I|re.M)`
 - `re.I` : `re.IGNORECASE` : Makes matching of alphabetic characters case-insensitive
 - `re.M` : `re.MULTILINE` : Causes start-of-string and end-of-string anchors to match embedded newlines
 - `re.S` : `re.DOTALL` : Causes the dot metacharacter to match a newline
 - `re.X` : `re.VERBOSE` : Allows inclusion of whitespace and comments within a regular expression
 - `re.DEBUG`: Causes the regex parser to display debugging information to the console
 - `re.A` : `re.ASCII` : Specifies ASCII encoding for character classification
 - `re.U` : `re.UNICODE` : Specifies Unicode encoding for character classification
 - `re.L` : `re.LOCALE` : Specifies encoding for character classification based on the current locale

# Without regex
 - contains : `"123" in "12345"`
 - index : `"toto12345".find("23")`
 - find : `"toto12345".index("23")`


# Ressources 
- https://realpython.com/regex-python/
- https://regex101.com/