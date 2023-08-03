# Python Reference for programming

This code reference is supposed to give an overview about the syntax and the elements of the Python programming language.  

## Data Types
### 
### Numeric Types
### Sequences Types

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

## Loops
For-loop in Python
```Python
for i in range(10):
    print(i)
```
For-each loop in Python
```Python
my_list = [1, 2, 5]
for x in my_list:
    print(x)
```
While loop in Python
```Python
n = 10
while n > 0:
    print(n)
    n -= 1
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
class ClassName:
    """
    Documentation of the class
    """
    def __init__(self, par, *args, **kwargs):
        self._par = par

    def update_par(self, par):
        self._par = par

    def read_par(self):
        return self._par
```
