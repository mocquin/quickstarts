```python
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(x, y)
print(model.coef_)
print(model.intercept_)

# estimate result for x=20
print(model.predict(20))
```


```python
# polynom
import numpy as np
from sklearn.linear_model import LinearRegression
x_new = np.hstack([x, x**2, x**3, x**4])
model = LinearRegression()
model.fit(x_new, y)
print(model.coef_)
print(model.intercept_)
print(model.predict(x_new))

# equivalent to
from sklearn.preprocessing import PolynomialFeatures
poly = PolynomialFeatures(degree=4, include_bias=False)
x_new2 = poly.fit_transform()
model = LinearRegression()
model.fit(x_new, y)
print(model.coef_)
print(model.intercept_)
print(model.predict(x_new))
```