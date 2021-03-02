# Curve fit

```python
def model(time, gain):
    return 2*time*gain
# x samples
x_time = np.array([1, 2, 3, 4, 5])
# y samples
true_gain = 1.2
noise = np.random.randn(x_time.shape[0])
true_y = 2*x_time*true_gain
y_height = true_y + noise

scipy.optimize.curve_fit(model, x_time, y_height,
                         p0=[1]) # initial guess

```