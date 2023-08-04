# Python Reference for programming

This code reference is supposed to give an overview about the syntax and the elements of the Python programming language.  

## Data Types
### 
### Boolean Type
```Python
bt = True
bf = False
```
### Numeric Types
```Python
var_int = 1
var_floag = 2.3
```
### String Types
### Binary Types
### Sequence Types
#### List
We define a list as follows
```Python
my_list = [1, "b", 6.5, None]
```
#### Tuple
```Python
my_tuple = (1, 5, -9)
```
#### Range
### Mapping Types
#### Dictionary
```Python
my_dict = {"name": "A", "value": 5.53}
```
### Set Types
#### Set
#### Frozenset

## Conditions
In Python the conditional expressions are used as follows
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
    pass
```
While loop in Python
```Python
n = 10
while n > 0:
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
## Virtual Environments
There exist "venv" or "virtualenv" as virtual environment packages. The installation of "virtualenv" can be done via pip
```shell
python -m pip install virtualenv
```
### Venv
```shell
# UNIX/Linux
python -m venv myvenv         # Create
source myvenv/bin/activate    # Activate
deactivate                    # Deactivate

# Windows
python -m venv myvenv         # Create
.\myvenv\Scripts\activate     # Activate
deactivate                    # Deactivate
```
### Virtualenv
```shell
# UNIX/Linux
virtualenv myvenv             # Create
source myvenv/bin/activate    # Activate
deactivate                    # Deactivate

# Windows
python -m venv myvenv         # Create
.\myvenv\Scripts\activate     # Activate
deactivate                    # Deactivate
```
