# Python Reference for programming

This code reference is supposed to give an overview about the syntax and the elements of the Python programming language.  

## Conditions
The if is implemented as follows
```Python
if condition:
    pass
elif condition:
    pass
[...]
else:
    pass
```

## Functions
The basic syntax is given by
```Python
def func(par):
    """
    Documentation of the function
    """
    return 0
```

## Classes

The basic syntax is given by

```Python
class ClassName(object):
    """
    Documentation of the class
    """
    def __init__(self, par, *args, **kwargs):
        self.par = par
```
