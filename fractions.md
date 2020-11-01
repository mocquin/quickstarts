# fractions
 - fractions' doc : https://docs.python.org/3/library/fractions.html
 - numbers.Rational : https://docs.python.org/3/library/numbers.html#numbers.Rational
 
 
The `Fraction` class inherit from `numbers.Rational`, and implements conversions to complex and bool, real, imag, +, -, *, /, abs(), conjugate(), ==, and !=, float, math.trunc(), round(), math.floor(), math.ceil(), divmod(), //, %, <, <=, >, and >=.


```python
import fractions
from fractions import Fraction
import decimal
```
```python
print(Fraction(16, -10))
print(Fraction(123))
print(Fraction())
print(Fraction('3/7'))
print(Fraction(' -3/7 '))
print(Fraction('1.414213 \t\n'))
print(Fraction('-.125'))
print(Fraction('7e-6'))
print(Fraction(2.25))
print(Fraction(1.1))
from decimal import Decimal
print(Fraction(Decimal('1.1')))
```

```python
-8/5
123
0
3/7
-3/7
1414213/1000000
-1/8
7/1000000
9/4
2476979795053773/2251799813685248
11/10
```

```python
def expose_fraction(f):
    print(f"Fraction's numerator : {f.numerator}")
    print(f"Fraction's denominator : {f.denominator}")
    # new in 3.8 : print(f"Fraction's as_integer_ratio() : {f.as_integer_ratio()}")
    print(f"Class method from_float(flt) : {f.from_float(3.45)}")
    print(f"Class method from_decimal(dec) : {f.from_decimal(decimal.Decimal(3.2))}")
    print(f"Fraction's limit_denominator : {f.limit_denominator(max_denominator=10000)}")
    print(f"Floored : {f.__floor__()}")
    print(f"Ceil : {f.__ceil__()}")
    print(f"Round : {round(f)}")
```

```python
>>> expose_fraction(Fraction("3/7"))
Fraction's numerator : 3
Fraction's denominator : 7
Class method from_float(flt) : 3884354678607053/1125899906842624
Class method from_decimal(dec) : 3602879701896397/1125899906842624
Fraction's limit_denominator : 3/7
Floored : 0
Ceil : 1
Round : 0
```
    