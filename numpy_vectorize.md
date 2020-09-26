# Numpy.vectorize tutorial :
 
Function exists since at least numpy 1.3 (see the docs of old numpy version on https://docs.scipy.org/doc/).
As of today (08/2020), in numpy v1.19, https://numpy.org/doc/stable/reference/generated/numpy.vectorize.html, the function signature is :
 numpy.vectorize(pyfunc, otypes=None, doc=None, excluded=None, cache=False, signature=None)
The object is defined in https://github.com/numpy/numpy/blob/d34b9ead10e28e3a0a62d642a16efdae2030ed76/numpy/lib/function_base.py
 
## parameters

### excluded
excluded can be used when you want to vectorize a function that takes arrays as input, but don’t want some inputs to be vectorized on
excluded is an attribute of the vectorized function, whose values can be either the names of input to exclude, or the position of the input
 
from the doc of signature : By default, pyfunc is assumed to take scalars as input and output
the generalized universal function signature is explained here : https://numpy.org/devdocs/reference/c-api/generalized-ufuncs.html
 
Important from the doc : The vectorize function is provided primarily for convenience, not for performance. The implementation is essentially a for loop.

### Otypes 
Otypes allows to cast the output to a specific dtype. If no otype is given, the dtype is guessed by calling the function on the first element. Then the function will loop over all inputs and use this dytpe. BUT if each call is timy, you may want to save the result of the first call (the one used to guess the otype), and not compute it again.
 
# Analysis of source code :
- Init to create the function
- Call to use the decorated function, relies on self._vectorize_call, which itself:
 - Uses _vectorize_call_with_signature if a signature is used
 - Else relies on self._get_ufunc_and_otypes to create ufunc and otypes. Ufunc is the final call on inputs
 - A loop is called on the inputs args to create a liste of inputs: inputs = [array(a, copy=False, subok=True, dtype=object) for a in args]
 - Then the raw ouputs are computed with outputs = ufunc(*inputs)
 - array(
 
# Alternatives
apply along axis

Ressources :
https://numpy.org/devdocs/reference/generated/numpy.vectorize.html
https://www.w3resource.com/numpy/functional-programming/vectorize.php
https://stackoverflow.com/questions/60832551/numpy-vectorize-signature : about signature


https://stackoverflow.com/questions/5197650/broadcasting-a-python-function-on-to-numpy-arrays
https://stackoverflow.com/questions/29318459/python-function-that-handles-scalar-or-arrays
https://stackoverflow.com/questions/26542615/a-python-function-that-accepts-as-an-argument-either-a-scalar-or-a-numpy-array
https://stackoverflow.com/questions/4029001/getting-a-python-function-to-cleanly-return-a-scalar-or-list-depending-on-numbe
https://github.com/hgrecco/pint/issues/828

https://code-examples.net/en/q/339065
https://stackoverflow.com/questions/43722023/can-i-prevent-numpy-array-from-casting-the-elements-as-numpy-arrays
https://stackoverflow.com/questions/35215161/most-efficient-way-to-map-function-over-numpy-array
https://numpy.org/doc/stable/reference/generated/numpy.apply_along_axis.html