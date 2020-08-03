  Create mask : bpm_3d = np.broadcast_to(bpm2d, shape=data.shape).astype(np.bool)
-        Apply mask on sequence : np.ma.array(raw_data, mask=mask2d)
-        1D linear regeression : (slope, offset), cov = np.polyfit(x_data, y_data, 1, cov=True
-        Create polynome function from coefficients  : np.poly1d([2, 1]) gives 2*x +1
-        Count nans : np.coun_nonzero(np.isnan(arr))
-        Drop nan : arr = arr[np.logical_not(np.isnan(arr))]
-        Load csv : np.genfromtxt(“toto.csv”, delimiter=”;”)
-        Binning : if you want bins of shape (a, b) for an array of (rows, cols), your reshaping of it should be .reshape(rows // a, a, cols // b, b)
-        Duplication : np.repeat(np.repeat(mat, 2, axis=0), 2, axis=1)
-        Mask : valids = np.ones(shape_in); valids[pad_v:-pad_v, pad_h, -pad_h]= 0
-        N highiest values : x[np.argsort(x)[-n:]]



# dtype objects

 - `dt = np.dtype('<d')` : double-precision floating-point
 - `i4` : integer on 4 bytes (32 bits)
 
 dt.name  dt.byteorder, dt.itemsize)

dt = np.dtype([('country', 'S20'), ('density', 'i4'), ('area', 'i4'), ('population', 'i4')])
population_table = np.array([
    ('Netherlands', 393, 41526, 16928800),
    ('Belgium', 337, 30510, 11007020),]
    dtype=dt)
    
 - `<` means that encoding is little-endian : least significant is stored in smallest address
 - `>` means that encoding is big-endian : most significant byte is stored in smallest address
 
 
Numpy's data types : 
- bool_ : Boolean (True or False) stored as a byte 
- int_ : Default integer type (same as C long; normally either int64 or int32) 
- intc : Identical to C int (normally int32 or int64) 
- intp : Integer used for indexing (same as C ssize_t; normally either int32 or int64) 
- int8 : Byte (-128 to 127) 
- int16 : Integer (-32768 to 32767) 
- int32 : Integer (-2147483648 to 2147483647) 
- int64 : Integer (-9223372036854775808 to 9223372036854775807) 
- uint8 : Unsigned integer (0 to 255) 
- uint16 : Unsigned integer (0 to 65535) 
- uint32 : Unsigned integer (0 to 4294967295) 
- uint64 : Unsigned integer (0 to 18446744073709551615) 
- float_ : Shorthand for float64 
- float16 : Half precision float: sign bit, 5 bits exponent, 10 bits mantissa 
- float32 : Single precision float: sign bit, 8 bits exponent, 23 bits mantissa 
- float64 : Double precision float: sign bit, 11 bits exponent, 52 bits mantissa 
- complex_ : Shorthand for complex128 
- complex64 : Complex number, represented by two 32-bit floats (real and imaginary components)
- complex128 : Complex number, represented by two 64-bit floats (real and imaginary components)



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
i, u, f, S and U : define size as well : `i4`, etc