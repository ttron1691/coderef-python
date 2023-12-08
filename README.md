# Python Reference for programming
This code reference is supposed to give an overview about the syntax and the elements of the Python programming language. 
## Data Types
### Check for Data Type
We can check for the data type of a variable as follows
```Python
isinstance(var_name, var_type)
```
Example
```Python
a = 2
if isinstance(a, int):
   print("Integer type")
else:
   print("No Integer type")
```
### None Type
The type None is used to represent a variable which is empty. In other words, the None type can be associated with a pointer which does not point to a specific address in memory.
```Python
var_none = None
```
Example
```Python
if isinstance(var_none, None):
   print("None type")
```
### Boolean Type
```Python
bool_true = True
bool_false = False
```
### Numeric Types
```Python
var_int = 1
var_float = 3.14159265359
```
### String Types
In Python strings are represented via quoted expressions
```Python
s_var1 = "This is a string"
s_var2 = "a, b, c"
```
Futhermore, there exist various methods to manipulate strings
```Python
len(s)		         # String length
list(s)		         # Create list of separate strings ['t', 'e', 'x', 't']

s1 + s2		         # Concatenate strings
(s + ' ') * 3	     # Repeat string with separator
s.upper()		     # Upper case
s.lower()		     # Lower case
s.capitalize()	     # Capitalize
s.title()		     # Capitalize each new word
s.split(sep = 'e')	 # Split string, Example: ['t', 'xt']
s.split(sep = ' ')	 # Split text into single words
s[::-1]		         # Reverse a string
s.strip('te')	     # Remove parts of a string, Example: 'xt'
s.replace('e', 'E')  # Replace parts of a string, Example: 'tExt'
s.replace('.', '')   # Remove punctuation in a string
''.join(['a', 'b'])  # Join list of characters into a string, Example: 'ab'
s.count('e')	     # Count characters in string, Example: 1
s.find('e')	         # Find sub string in given string, Example: 1
```
### Binary Types
### Sequence Types
#### List
A list in Python is defined as a build-in mutable dynamic collection module container of objects. We characterize a list with square brackets
```Python
var_list = [1, 2, 3]
```
There are several methods defined for list creation and manipulation
```Python
append(x)        	    		# Add element x to end
extend(iterable) 	    		# Extend list 
insert(i, x)     	    		# Insert x at position i
remove(x)        	    		# Remove first element x
pop([i])         	    		# Remove and return item at i (last)
clear()                  		# Remove all items from list
index(x[, start[, end]]) 		# Return index in list of first item x
count(x) 		    		# Return number of times x appears
sort(*, key=None, reverse=False) 	# Sort (numerical) items in place
reverse()				# Reverse elements of list
copy()				# Return copy of the list
```
We give a few examples in the following
```Python 
my_list = [1, 2, 3]
sq_list = [x**2 for x in range(10)]
sq_list = list(map(lambda x: x**2, range(10)))
com_list = [(x, y) for x in [1,2,3] for y in [3,1,4] if x != y]
fil_list = [x for x in vec if x >= 0]
```
#### Tuple
```Python
my_tuple = (1, 5, -9)
```
#### Range
The range type represents an immutable sequence of numbers with syntax
```
class range(start, stop[, step])
```
It is commonly used for looping a specific number of times in for loops such as
We can define range iterators as follows
```Python
sum_iter = 0
for i in range(10):
    sum_iter += 1
```
We can also define lists by using range types
```Python
list(range(10))
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
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
Example
```Python
n = 10
if n < 10:
    print("n is smaller than 10")
elif n == 10:
    print("n is equal to 10")
else:
    print("n is larger than 10)"
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
## Input and Output
```Python
# Console input
inp = input('This is your input: ')
print('Your input: ' + inp)

# File object read methods, n: byte number
read(size=-1)      # read complete content
readline(size=-1)  # read a single line
readlines()        # read complete content and return list

# Read content of a given file [file_name='my_file.txt']
with open(file_name, 'r') as file_stream:
    file_content = file_stream.read()

# File object write methods [file_name='output.txt']
write(string)      # writes string to a file
writelines(seq)    # writes sequence to a file
with open(file_name, 'w') as file_stream:
    file_stream.write(my_data)
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
### Abstract (Base) Classes
### Inheritance
## Decoratos
## Generators
## Exceptions
The typical structure for catching or throwing exceptions is given by
```Python
try:
    # Some code
except SomeException:
    tb = sys.exception().__traceback__
    raise OtherException(...).with_traceback(tb)
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
## Standard Library
### Web protocol and data handling
### JSON Package
```Python
# json.load()
# json.dump(obj, fp, *, …, indent=None, …, **kw)
# json.dumps(obj, *, …, **kw)

# Read JSON file [e.g. file_name = 'file.json']
with open(file_name, 'r') as file_reader:
    data = json.load(file_reader)

# Write JSON file [e.g. file_name = 'my_output.json']
with open(file_name, 'w') as file_writer:
    json.dump(output_data, file_writer, indent=4)
```
### Requests Package
```Python
# Install
python -m pip install requests
# Import
import requests

# Response object
response.status_code 		# Attribute: response status code
response.headers['Content-Type']	# Attribute: response headers
response.json()			# Method: receive json-object

api_url = 'https://apiurl.com/post'	# URL for the API

# GET request
response = requests.get(api_url) 
response_json = response.json() 	# Example: {'userID': 1, 'text': 'text_example'}

# POST request
response = requests.post(api_url, json={'id': 2, 'title': 'text'})
response = requests.post(api_url, json={'id': 2, 'title': 'text'}, headers={'Content-Type': 'application/json'})

# PUT request 
response = requests.post('https://apiurl.com/put', )
```
### Operating System Services
#### Logging
#### Command Line Arguments
### Database Connection
#### SQLite
### Graphical User Interfaces
#### Tkinter
