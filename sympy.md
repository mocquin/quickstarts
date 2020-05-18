Solve linar system equation
```
from sympy import symbols
from sympy.solvers.solveset import linsolve
x, y, z = symbols('x, y, z')
linsolve([2*x+y-13,
          10*x-2*y-44], (x, y))
```