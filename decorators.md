
# ressources 
 - realpython primer on decorators : https://realpython.com/primer-on-python-decorators/

# Good pratice : 

```python
import functools
 
def do_twice(func):
    @functools.wraps(func)
    def wrapper_do_twice(*args, **kwargs):
        func(*args, **kwargs)
        return func(*args, **kwargs)
    return wrapper_do_twice

```



For a class-based decorator : 

```python
import functools

class CountCalls:
    def __init__(self, func):
        functools.update_wrapper(self, func)
        self.func = func
        self.num_calls = 0

    def __call__(self, *args, **kwargs):
        self.num_calls += 1
        print(f"Call {self.num_calls} of {self.func.__name__!r}")
        return self.func(*args, **kwargs)

@CountCalls
def say_whee():
    print("Whee!")

```

# Introspect functions

```python
"Mathematical operations"

def addition(a:int, b:int) -> int:
    """
    Return the sum of the two numbers `a` and `b`

    ex: addition(3, 5) -> 8
    """
    return a + b


import inspect
from operations import addition
inspect.getdoc(addition)
# 'Return the sum of the two numbers `a` and `b`\n\nex: addition(3, 5) -> 8'
inspect.getsource(addition)
# 'def addition(a:int, b:int) -> int:\n    [...]\n    return a + b\n'
inspect.getsourcefile(addition)
# '/home/entwanne/operations.py'
# inspect.getmodule(addition)
<module 'operations' from '/home/entwanne/operations.py'>
# inspect.getsourcelines(addition)
(['def addition(a:int, b:int) -> int:\n', ..., '    return a + b\n'], 3)

sig = inspect.signature(addition)
print(sig)
# (a:int, b:int) -> int

sig.return_annotation
#<class 'int'>
for param in sig.parameters.values():
     print(param.name, param.default, param.annotation, param.kind)

a <class 'inspect._empty'> <class 'int'> POSITIONAL_OR_KEYWORD
b <class 'inspect._empty'> <class 'int'> POSITIONAL_OR_KEYWORD
```