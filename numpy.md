# Load data from file 

 - `np.loadtxt(path, delimiter= » ; », skiprows=1)`
 - `np.genfromtxt(path, delimiter=”;”, names=True)`


# Misc

 - get n highiest values : `x[np.argsort(x)[-n:]]`

# Array
 - transpose : `np.transpose(0, 2, 1)` to switch axis
`

# Masked array

 - Extend 2d mask to 3d : `mask3d = np.broadcast_to(mask2d, shape=data.shape).astype(np.bool)`
 - Apply mask : `np.ma.array(raw_data, mask=mask2d)`
 - Edge mask : `valids = np.ones(shape_in); valids[pad_v:-pad_v, pad_h, -pad_h]= 0`
 - disk mask : 
```python
import matplotlib.pyplot as plt
import numpy as np
 
x_ = np.linspace(-10, 10, 1000)
y_ = np.linspace(-10, 10, 1000)
 
X, Y = np.meshgrid(x_, y_)
 
radius = 8
disk_mask = (X ** 2) + (Y ** 2) < radius ** 2
 
plt.matshow(disk_mask, cmap="gray", extent=[-10, 10, -10, 10])
plt.show()

```



# Linear regression and polynom

 - 1D linear regeression : `(slope, offset), cov = np.polyfit(x_data, y_data, 1, cov=True)`
 - Create polynome function from coefficients  : `np.poly1d([2, 1])` gives 2\*x +1


# Solving

 - Solve linear equation system
```python
import numpy as np

# eq1 = Eq( 2 * x +-1 * y, -4)
# eq2 = Eq( 3 * x +-1 * y, -2)
 
eq1_coefs = [2, -1]
eq2_coefs = [3, -1]
cons_coefs = [-4, -2]
nmat = np.array([eq1_coefs, eq2_coefs])
cons = np.array(cons_coefs)
np.linalg.solve(nmat, cons)
 
# other method
cons = np.array([-4, -2])
A = np.array([eq1_coefs, eq2_coefs])
X = np.linalg.inv(A).dot(cons)
```


# 3d plotting
 - Create a grid for plotting : 
```python
xplot = np.outer(np.linspace(-5, 5, 100), np.ones(100))
yplot = xplot.T
```

# Nans

 - Count nans : `np.coun_nonzero(np.isnan(arr))`
 - Drop nan : `arr = arr[np.logical_not(np.isnan(arr))]`
 - Get indices of non nan : `np.argwhere(~np.isnan(arr))`

# Image processing

 - Duplication : `np.repeat(np.repeat(mat, 2, axis=0), 2, axis=1)`
 - Binning : if you want bins of shape (a, b) for an array of (rows, cols), your reshaping of it should be .reshape(rows // a, a, cols // b, b)


# Merge, concatenate
`np.concatenate((a1, a2, ...), axis=0, out=None)`


# dtype objects

Attributes : 
 - `dt.name`
 - `dt.byteorder`
 - `dt.itemsize`

Example : 

```python
dt = np.dtype([('country', 'S20'),
               ('density', 'i4'), 
               ('area', 'i4'), 
               ('population', 'i4')])
population_table = np.array([
    ('Netherlands', 393, 41526, 16928800),
    ('Belgium', 337, 30510, 11007020),]
    dtype=dt)
```

Numpy's data types : 
 - `bool_` : Boolean (True or False) stored as a byte 
 - `int_` : Default integer type (same as C long; normally either int64 or int32) 
 - `intc` : Identical to C int (normally int32 or int64) 
 - `intp` : Integer used for indexing (same as C ssize_t; normally either int32 or int64) 
 - `int8` : Byte (-128 to 127) 
 - `int16` : Integer (-32768 to 32767) 
 - `int32` : Integer (-2147483648 to 2147483647) 
 - `int64` : Integer (-9223372036854775808 to 9223372036854775807) 
 - `uint8` : Unsigned integer (0 to 255) 
 - `uint16` : Unsigned integer (0 to 65535) 
 - `uint32` : Unsigned integer (0 to 4294967295) 
 - `uint64` : Unsigned integer (0 to 18446744073709551615) 
 - `float_` : Shorthand for float64 
 - `float16` : Half precision float: sign bit, 5 bits exponent, 10 bits mantissa 
 - `float32` : Single precision float: sign bit, 8 bits exponent, 23 bits mantissa 
 - `float64` : Double precision float: sign bit, 11 bits exponent, 52 bits mantissa 
 - `complex_` : Shorthand for complex128 
 - `complex64` : Complex number, represented by two 32-bit floats (real and imaginary components)
 - `complex128` : Complex number, represented by two 64-bit floats (real and imaginary components)

Data type syntax :

 - `b` : boolean
 - `i` : (signed) integer
 - `u` : unsigned integer
 - `f` : floating-point
 - `c` : complex-floating point
 - `m` : timedelta
 - `M` : datetime
 - `O` : (Python) objects
 - `S` :'a' − (byte-)string
 - `U` : Unicode
 - `V` : raw data (void)
 - `<` means that encoding is little-endian : least significant is stored in smallest address
 - `>` means that encoding is big-endian : most significant byte is stored in smallest address
 
i, u, f, S and U : define size as well : `i4`, etc

Example : 
 - `dt = np.dtype('<d')` : double-precision floating-point
 - `i4` : integer on 4 bytes (32 bits)