https://towardsdatascience.com/optimization-with-constraints-using-lagrange-multiplier-in-python-82769c9a43fe

# Solve linar system equation
```python
from sympy import symbols
from sympy.solvers.solveset import linsolve
x, y, z = symbols('x, y, z')
linsolve([2*x+y-13,
          10*x-2*y-44], (x, y))
```


# Solve equation system
```python
from sympy import *

s, t, l = symbols('s t l')
solve(
    [Eq((21/4)*((t**(1/4))/s**(1/4)) - 25*l, 0),
     Eq((7/4)*(s**(3/4)/t**(3/4)) - 250*l, 0),
     Eq(25*s+250*t - 2500, 0)
    ],
    [s,t,l], simplify=False)
```


# Derivatives
To create a Derivative object : 
```python
from sympy import Derivative 
d=Derivative(expr) 
d
```
Then to compute the derivative : 
```python
d.doit()
```
To compute derivative : 
```python
diff(expr,x)
diff(expr,x, 3)
expr.diff(x, 3)
expr.diff((x, n))
diff(expr, x, y, y, z, z, z, z)
```


```python
diff(expr, x, y, y, z, z, z, z)

# from expr with undefined numbers of derivation 
m, n, a, b = symbols('m n a b')
expr = (a*x + b)**m
expr.diff((x, n)) # use tuple
```