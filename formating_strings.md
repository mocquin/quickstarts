# Formating mini language
The formatting can be split in 3 : `[name][!conversion][:format_spec]`
 - `name` : the object to be formatted : Specifies the source of the value to be formatted : variable, or number if using numbering or key if using dictering
 - `conversion` : convert object with str, repr, or ascii : Indicates which standard Python function to use to perform the conversion, among !s for str(), !r for repr() and !a for ascii()
 - `format_spec` : format specification : Specifies more detail about how the value should be converted
    
## conversion
 - `!s` : Convert with str()
 - `!r` : Convert with repr()
 - `!a` : Convert with ascii()

## format spec

The format spec can be split in 

`:[[fill]align][sign][#][0][width][group][.prec][type]`

Examples : 
 - `"{: < -10.3f}"` : left align, padded with space, width 10, use sign on negativ number and space on positiv, 3 fixed point value, fixed point type format
 - `"{: >-12.3f}"` : Right align padded with 0, width 12, precision 3
 - `"{:*^15}"` : center-aligned with 15 total width, pad with *

Details on format spec : 
 - `fill` : any character to pad values that don’t occupy the entire field width
 - `align` : Specifies how to justify values that don’t occupy the entire field width
  - `<` : left aligned
  - `>` : right ligned
  - `^` : centered
  - `=` : for numericals, if sign is used and align is =, the sign is placed at the extrem left, not next to the digit
 - `sign`: Controls whether a leading sign is included for numeric values
  - `+` : sign always appended
  - `-` : sign appended if negative value
  - ` ` : space if positive, `-` if negative
 - `#` : Selects an alternate output form for certain presentation types
 - `0` : Causes values to be padded on the left with zeros instead of ASCII space characters
 - `width`: any number : Specifies the minimum width of the output
 - `group` : Specifies a grouping character for numeric output
  - `_`
  - `,`
 - `prec` : any number : Specifies the number of digits after the decimal point for floating-point presentation types, and the maximum output width for string presentations types
 - `type` : Specifies the presentation type, which is the type of conversion performed on the corresponding argument
  - `b` : Binary integer
  - `c` : Single character
  - `d` : Decimal integer
  - `e` or `E` : Exponential
  - `f` or `F` : Floating point
  - `g` or `G` : Floating point or Exponential
  - `o` : Octal integer
  - `s` : String
  - `x` or `X` : Hexadecimal integer
  - `%` : Percentage
  
  
# String formatting
 
```python
name = "Toto"
age = 5
```

3 ways :
 - Old %-style : OG : `print("Toto is %s" % age)` see https://docs.python.org/3/library/stdtypes.html#printf-style-string-formatting
 - Str.format method : since 2.6 : `print(“Toto is {}”.format(age)` see https://docs.python.org/3/library/stdtypes.html#str.format
 - F-string, since 3.6 : `print(f”Toto is {age}”)`
 
Note that str.format and f-string rely on __format__ if available, else __str__.
 
 
## Tips and tricks with %-formating
`print('%d %s cost %.2f' % (6, 'bananas', 1.74))`


## Tips and tricks with str.format
- Automatic field numbering : `"Hello, {}. You are {}.".format(name, age)`
- Numbering : `"Hello, {1}. You are {0}.".format(age, name)`
- Dictering : `person = {'name': 'Toto', 'age': 5};print("Hello, {name}. You are {age}.".format(name=person['name'], age=person['age']))`:
- Dictering bis : `print("Hello, {name}. You are {age}.".format(**person))`
- Lookup table or keyword replacement fields with the same name :
```python
print('{quantity} {item} cost {price}'.format(
     quantity=6,
     item='bananas',
     price=1.74))
```

 
## Tips and tricks with f-string
 
 - Use repr instead of str : `f"{new_comedian!r}"`
 - Multiline f-string : tuple-way :
```python
message = (
f"Hi {name}. "
f"You are a {profession}. "
f"You were in {affiliation}."
)
```
 - Multiline f-string : backslash-escape way :
```python
message = f"Hi {name}. " \
          f"You are a {profession}. " \
          f"You were in {affiliation}."
```

  
# Pros and cons
- % notation (OG) : verbose, error-prone with tuples
- str.format (since 2.6) : verbose
- f-string (since 3.6) : evaluated at runtime then formated using __format__ protocol

  
# Ressources
 - https://realpython.com/python-formatted-output/
 - https://docs.python.org/3/library/string.html#formatspec
 - https://docs.python.org/3/library/string.html#formatstrings
 - https://docs.python.org/3/library/string.html#string-formatting 
 - https://kapeli.com/cheat_sheets/Python_Format_Strings.docset/Contents/Resources/Documents/index
 - https://cheatography.com/mutanclan/cheat-sheets/python-string-formatting/   
 - https://realpython.com/python-string-formatting/
