# Python Reference for programming
This code reference is supposed to give an overview about the syntax and the elements of the Python programming language. 

# Table of Contents
- [Download and installation](#download-and-installation)
- [Data Types](#data-types)
- [Documentation](#documentation)
- [Standard Library](#standard-library)
- [Pytest](#pytest)

## Download and installation
We can download the build files for various operating systems on the official Python website [https://www.python.org/](https://www.python.org/).
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
In Python a dictionary represents a build-in mutable dynamic collection module container of objects (associative arrays). Dictionaries are collections of key-value pairs, with unique key-list. We can declare a dictionary via curly brackets
```Python
my_dict = {
    <key_1>: <value_1>,
    <key_2>: <value_2>,
    …
    <key_n>: <value_n>
}
```
The following methods are used to create or manipulate the data of a dictionary
```Python
clear()			                # Remove all elements
copy()			                # Return copy of given dictionary
fromkeys(keys[,value])	        # Create empty dictionary from keys iterable
get(keyname [,value])	        # Return dictionary value for given key
items()			                # Return view object to dictionary items
keys()			                # Return view object to dictionary keys [list(my_dict.keys())]
pop(keyname)		            # Remove key-value pair from dictionary and returns it
popitem()			            # Remove object that was last inserted (old: remove random object)
setdefault(keyname [,value])	# Return value of item with specific key (set if not exists) 
update(iterable)		        # Insert specified items to the dictionary
values()			            # Return view object to dictionary values [list(my_dict.values())]
```
We can iterate over the key value pairs of a dictionary in the following way
```Python
for key, value in my_dict.items():
    print(key, value)
```
Examples
```Python
var_dict = {"key_1": 1,
            "key_2": 2.53,
            "key_3": "text"}
my_dict = {'a': 1, 'b': 'text', 'c': 12.284}
my_dict_num = {x: x**2 for x in (2, 4, 6)} # Result: {2: 4, 4: 16, 6: 36}
```
### Set Types
#### Set
#### Frozenset
## Style
### Line breaks
Considering styling and readability of code we follog the PEP 8 style guide recommendations. The correct way to handle line breaks for different situations is given as follows
```Python
# Aligned with opening delimiter
foo = long_function_name(var_one, var_two,
                         var_three, var_four)

# Add 4 spaces (an extra level of indentation) to distinguish arguments from the rest.
def long_function_name(
      var_one, var_two, var_three,
      var_four):
   print(var_one)

# Hanging indents should add a level.
foo = long_function_name(
   var_one, var_two,
   var_three, var_four)
```
Considering line breaks for if statements we proceed as follows
```Python
# No extra indentation.
if (this_is_one_thing and
    that_is_another_thing):
    do_something()

# Add a comment, which will provide some distinction in editors
# supporting syntax highlighting.
if (this_is_one_thing and
    that_is_another_thing):
    # Since both conditions are true, we can frobnicate.
    do_something()

# Add some extra indentation on the conditional continuation line.
if (this_is_one_thing
      and that_is_another_thing):
   do_something()
```
### Method chaining
Concerning method chaining a single line with multiple chained method calls may suffer from good readability.

We can use backslashes allowing a line to continue beyond a line break
```Python
df_input = pd.read_csv("data/input/extract_test.csv", index_col=0) \
             .drop(columns="my_col") \
             .sort_values("index") \
             .head(1)
```
Furthermore, we may use parentheses () for which free line breaks are allowed
```Python
df_input = (
   pd.read_csv("data/input/extract_test.csv", index_col=0)
   .drop(columns="my_col")
   .sort_values("index")
   .head(1)
)
```
We can also use parentheses () for a standalone statement instead of assigning a value to a variable
```Python
(
   spark.createDataFrame(df).write
   .format("csv")
   .mode("overwrite")
   .save("/tmp/output/test_data")
)
```
## Documentation
We focus on the Google style format for Python in the following. The basic structure of the documentation docstring looks as follows
```Python
"""Fetches rows from a Smalltable.
    Args:
        parameter_one: The first parameter.
        parameter_two: The second parameter
          with a second line.

    Returns:
        A pandas DataFrame including the cleaned data

        {'data': ["a", "b", "c"],
         'value': [1, 2, 3]}

        If a key from the keys argument is missing from the dictionary, 
        then that row was not found in the DataFrame.

    Raises:
        IOError: An error occurred accessing the smalltable.
    """
```
A function is documented in the following way
```Python
# Example method
def fetch_smalltable_rows(
    table_handle: smalltable.Table,
    keys: Sequence[bytes | str],
    require_all_keys: bool = False,
) -> Mapping[bytes, tuple[str, ...]]:
    """Fetches rows from a Smalltable.

    Retrieves rows pertaining to the given keys from the Table instance
    represented by table_handle.  String keys will be UTF-8 encoded.

    Args:
        table_handle: An open smalltable.Table instance.
        keys: A sequence of strings representing the key of each table
          row to fetch.  String keys will be UTF-8 encoded.
        require_all_keys: If True only rows with values set for all keys will be
          returned.

    Returns:
        A dict mapping keys to the corresponding table row data
        fetched. Each row is represented as a tuple of strings. For
        example:

        {b'Serak': ('Rigel VII', 'Preparer'),
         b'Zim': ('Irk', 'Invader'),
         b'Lrrr': ('Omicron Persei 8', 'Emperor')}

        Returned keys are always bytes.  If a key from the keys argument is
        missing from the dictionary, then that row was not found in the
        table (and require_all_keys must have been False).

    Raises:
        IOError: An error occurred accessing the smalltable.
    """
```
A class is documented in the following way
```Python
class SampleClass:
    """Summary of class here.

    Longer class information...
    Longer class information...

    Attributes:
        likes_spam: A boolean indicating if we like SPAM or not.
        eggs: An integer count of the eggs we have laid.
    """

    def __init__(self, likes_spam: bool = False):
        """Initializes the instance based on spam preference.

        Args:
          likes_spam: Defines if instance exhibits this preference.
        """
        self.likes_spam = likes_spam
        self.eggs = 0

    def public_method(self):
        """Performs operation."""

```
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
    # Some code
```
A typical workflow for exception handling looks as follows
```Python
try:
    # Some code which may result in an exception case
except SomeException1 as e:
    # Consider check for exception one
except SomeException1 as e:
    # Consider check for exception two
except Exception as e:
    # Handle other exceptions at this point
```
We can also define a custom exception in Python
```Python
class CustomException(Exception):
    pass
```
This can be used as follows
```Python
try:
    if condition:
        raise CustomException("An error occured during the condition check.")
except CustomException as e:
    # Handle the custom exception
except Exception as e:
    # Handle other exceptions at this point
```
We can also define either an else or a finally section after the try/except blocks
```Python
try:
    # Some code which may result in an exception case
except SomeException1 as e:
    # Consider check for exception one
except SomeException1 as e:
    # Consider check for exception two
except Exception as e:
    # Handle other exceptions at this point
else:
    # Code which will be executed if there are no exceptions
```
Additionally, we give the finally section here
```Python
try:
    # Some code which may result in an exception case
except Exception as e:
    # Handle other exceptions at this point
else:
    # Code which will be executed if there are no exceptions
finally:
    # Code which will be always executed 
```
## Python Typing
The typing library is used as a tool to provide the developer hints and details about the data types of variables, primarily used in function or method definitions. Basically, the parameters and the return type of a method can receive a type hint as well as all variables which are initialized in the code. 
### Build-in types
The basic notation for internal build-in data types like int, str, float, bool, None works as follows
```Python
def add(x: int, y: int) -> int:
    return x + y
```
### Collections
In terms of collections we can use the following
```Python
from typing import List, Dict, Tuple

def get_names(ages: Dict[str, int]) -> List[str]:
    return list(ages.keys())

def process_coordinates(coords: Tuple[int, int, int]) -> str:
    return f"Coordinates: {coords}"
```
We may think of the generic types
* List[T]: A list containing elements of type T
* Dict[K, V]: A dictionary with keys of type K and values of type V
* Tuple[T1, T2, ...]: A tuple with specified types for each element

### Optional values
The optional type hint is used for variables or arguments that my be of type None
```Python
from typing import Optional

def greet(name: Optional[str] = None) -> str:
    return f"Hello, {name}" if name else "Hello, Stranger"

```

### Union
The Union type hint is used for variables that can have multiple types
```Python
from typing import Union

def parse_input(value: Union[int, str]) -> int:
    return int(value)
```

### Callable

The callable type hint is used to specify functions or callbacks within a specific signature
```Python
from typing import Callable

def operate(a: int, b: int, func: Callable[[int, int], int]) -> int:
    return func(a, b)
```

### Type aliases

We can also define custom aliases for more complex data types in the following way
```Python
from typing import List

Vector = List[float]

def scale(vector: Vector, factor: float) -> Vector:
    return [x * factor for x in vector]
```

### Generics
The TypeVar is used to create generic functions or classes
```Python
from typing import TypeVar, List

T = TypeVar('T')  # Can be any type

def get_first_element(items: List[T]) -> T:
    return items[0]
```

### Any type
The Any type hint allows any type and is used in the following way
```Python
from typing import Any

def handle_dynamic_input(data: Any) -> None:
    print(data)  # Accepts any type

```

### Final
The Final type hint is used for immutable variables in the following way
```Python
from typing import Final

PI: Final = 3.14159
```

### Literal
Using literal we can restrict variables to specific values 
```Python
from typing import Literal

def set_mode(mode: Literal['read', 'write']) -> None:
    pass

set_mode('read')  # Valid
set_mode('execute')  # Type error
```


## Python Packages
We can import python files as modules which is beneficial in terms of software development efforts including multiple source files structured within directories. We start with the following structure of code
```shell
package/
└── src/
    └── utils
        ├── __init__.py
        └── readwrite.py
    main.py
```
The readwrite module looks as follows
```Python
# src/utils/readwrite.py
def rw_function():
   pass
```
Within the main file, the readwrite module can be import as follows
```Python
# src/main.py
from utils.readwrite import rw_function
```
The __init__.py file indicates that the directory is considered as a Python package. The __init__.py file can contain the imports of modules, for instance
```Python
# src/utils/__init__.py
from .readwrite import rw_function
```
Then, within the main.py file we can simply import the module as follows
```Python
# src/main.py
from utils import readwrite
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

### Pydantic
The basic element of Pydantic is the model creation and validation
```Python
from pydantic import BaseModel
from typing import Optional, Literal

class User(BaseModel):
    id: int
    name: str
    age: int
    email: str
    employment_status: Literal['working', 'retired']
    is_active: bool = True
    information: Optional[str] = None

# Example Usage
user = User(id=1, name="Alice", age=25, email="alice@example.com", employment_status="working")

# Conversion to Python dictionary
user.dict()
```

# Python Pydantic Reference Card

## Basic Usage

### Installation
```python
pip install pydantic
```

### Simple Model
```python
from pydantic import BaseModel

class User(BaseModel):
    id: int
    name: str
    email: str
    active: bool = True  # Default value
```

### Type Validation
```python
user = User(id=1, name="John Doe", email="john@example.com")  # Valid
user = User(id="1", name="John Doe", email="john@example.com")  # Coerces "1" to int(1)

try:
    User(id="not-an-int", name="John Doe", email="john@example.com")
except:
    print("Validation error: id must be an integer")
```

### Model Methods
```python
# Dictionary conversion
user_dict = user.model_dump()  # In v2+, was .dict() in v1
user_json = user.model_dump_json()  # In v2+, was .json() in v1

# Copy and update
user2 = user.model_copy(update={"name": "Jane Doe"})  # In v2+, was .copy() in v1
```

## Field Types and Validation

### Common Types
```python
from datetime import datetime
from typing import List, Dict, Optional, Union
from uuid import UUID
from pydantic import BaseModel, EmailStr, HttpUrl, conint, confloat

class AdvancedUser(BaseModel):
    id: int
    name: str
    email: EmailStr  # Validates email format
    website: HttpUrl  # Validates URL format
    tags: List[str] = []
    metadata: Dict[str, str] = {}
    last_login: Optional[datetime] = None
    score: Union[int, float] = 0.0
    age: conint(ge=0, lt=120)  # Constrained integer
    rating: confloat(ge=0, le=5)  # Constrained float
    user_id: UUID  # UUID validation
```

### Field Configuration
```python
from pydantic import BaseModel, Field

class Product(BaseModel):
    id: int
    name: str = Field(..., min_length=3, max_length=50)
    price: float = Field(gt=0, description="Price must be positive")
    description: Optional[str] = Field(
        None,
        title="Product description",
        max_length=1000,
        examples=["A great product"]
    )
    sku: str = Field(regex=r"^[A-Z]{3}-\d{4}$")
```

## Advanced Validation

### Validators
```python
from pydantic import BaseModel, field_validator, model_validator

class Order(BaseModel):
    id: int
    items: List[str]
    total: float
    
    # Field validator (single field)
    @field_validator('items')
    def check_items_not_empty(cls, v):
        if not v:
            raise ValueError('Order must have at least one item')
        return v
    
    # Model validator (multiple fields)
    @model_validator(mode='after')
    def check_total(self):
        if len(self.items) > 5 and self.total < 100:
            raise ValueError('Large orders should have higher total')
        return self
```

### Custom Types
```python
from pydantic import BaseModel, GetCoreSchemaHandler
from pydantic.json_schema import JsonSchemaValue
from pydantic_core import CoreSchema, core_schema

class ISBN10:
    def __init__(self, value: str):
        if not self._is_valid(value):
            raise ValueError(f"Invalid ISBN-10: {value}")
        self.value = value
        
    @staticmethod
    def _is_valid(value: str) -> bool:
        # Simple validation for example
        return len(value) == 10
        
    def __repr__(self) -> str:
        return f"ISBN10({self.value!r})"
        
    @classmethod
    def __get_pydantic_core_schema__(
        cls, _source_type, _handler: GetCoreSchemaHandler
    ) -> CoreSchema:
        return core_schema.with_info_plain_validator_function(
            cls._validate,
            serialization=core_schema.str_serializer(),
            type=cls,
        )
    
    @classmethod
    def _validate(cls, value, info):
        if isinstance(value, cls):
            return value
        if isinstance(value, str):
            return cls(value)
        raise ValueError(f"Cannot convert {value} to {cls.__name__}")

class Book(BaseModel):
    title: str
    isbn: ISBN10
```

## Nested Models

### Model Composition
```python
from pydantic import BaseModel
from typing import List

class Address(BaseModel):
    street: str
    city: str
    country: str
    postal_code: str

class User(BaseModel):
    id: int
    name: str
    addresses: List[Address]

# Usage
user = User(
    id=1,
    name="John",
    addresses=[
        {"street": "123 Main St", "city": "New York", "country": "USA", "postal_code": "10001"},
        {"street": "456 Park Ave", "city": "Boston", "country": "USA", "postal_code": "02108"}
    ]
)
```

### Recursive Models
```python
from pydantic import BaseModel
from typing import List, Optional

class Comment(BaseModel):
    id: int
    text: str
    replies: List['Comment'] = []

Comment.model_rebuild()  # Required for recursive models in v2
```

## Config and Settings

### Model Config
```python
from pydantic import BaseModel, ConfigDict
from datetime import datetime

class User(BaseModel):
    model_config = ConfigDict(
        extra='forbid',  # Raise error if extra fields provided
        str_strip_whitespace=True,  # Strip whitespace from strings
        validate_assignment=True,  # Validate attributes on assignment
        frozen=False,  # If True, models are immutable
        populate_by_name=True,  # Allow population by field name and alias
        json_schema_extra={
            'examples': [
                {
                    'id': 123,
                    'name': 'John Doe',
                    'signup_ts': '2020-01-01T00:00:00Z'
                }
            ]
        }
    )
    
    id: int
    name: str
    signup_ts: datetime
```

### Settings Management
```python
from pydantic import BaseModel, Field
from pydantic_settings import BaseSettings
from typing import Optional

class DatabaseSettings(BaseModel):
    host: str
    port: int
    user: str
    password: str
    
class AppSettings(BaseSettings):
    app_name: str = "My App"
    debug: bool = False
    db: DatabaseSettings
    log_level: str = Field('INFO', env='LOG_LEVEL')
    
    model_config = {
        'env_nested_delimiter': '__',
        'env_file': '.env',
        'env_file_encoding': 'utf-8',
        'env_prefix': 'MYAPP_',
    }

# Usage
# Environment variables like:
# MYAPP_APP_NAME=MyApp
# MYAPP_DB__HOST=localhost
settings = AppSettings()
```

## Serialization & Deserialization

### JSON Schema Generation
```python
from pydantic import BaseModel
from typing import List

class Item(BaseModel):
    name: str
    price: float

class Order(BaseModel):
    id: int
    items: List[Item]

# Generate JSON schema
schema = Order.model_json_schema()
print(schema)
```

### Custom Serialization
```python
from pydantic import BaseModel, field_serializer, field_validator
from datetime import datetime
import json

class LogEntry(BaseModel):
    timestamp: datetime
    level: str
    message: str

    @field_serializer('timestamp')
    def serialize_timestamp(self, value):
        return value.strftime("%Y-%m-%d %H:%M:%S")
        
    @field_serializer('level')
    def serialize_level(self, value):
        return value.upper()
```

### Computed Fields
```python
from pydantic import BaseModel, computed_field
from typing import List

class Order(BaseModel):
    items: List[dict]
    tax_rate: float = 0.1
    
    @computed_field
    def subtotal(self) -> float:
        return sum(item.get('price', 0) for item in self.items)
        
    @computed_field
    def tax(self) -> float:
        return self.subtotal * self.tax_rate
        
    @computed_field
    def total(self) -> float:
        return self.subtotal + self.tax
```

## Best Practices

### Error Handling
```python
from pydantic import BaseModel, ValidationError

class User(BaseModel):
    id: int
    email: str

try:
    user = User(id="not-an-int", email="invalid-email")
except ValidationError as e:
    print(f"Validation errors: {e.errors()}")
    # Access specific errors
    for error in e.errors():
        print(f"Field: {error['loc'][0]}, Error: {error['msg']}")
```

### Type Annotations
```python
# Prefer these imports for better type checking
from typing import Dict, List, Optional, Union, Any, Literal
from pydantic import BaseModel

# Use specific types when possible
class Config(BaseModel):
    mode: Literal["development", "testing", "production"]
    flags: Dict[str, bool]
    counts: Dict[str, int]
    # Avoid using Any when possible
    # metadata: Dict[str, Any]  # Less ideal
    metadata: Dict[str, Union[str, int, bool]]  # Better
```

### Performance Tips
```python
from pydantic import BaseModel, Field, model_validator

# 1. Use validators sparingly - they impact performance
class EfficientModel(BaseModel):
    # 2. Use default values where appropriate
    count: int = 0
    
    # 3. Use Field constraints instead of validators when possible
    name: str = Field(..., min_length=2, max_length=50)
    
    # 4. For complex validation, use model_validator instead of multiple field validators
    @model_validator(mode='after')
    def validate_model(self):
        # Validate related fields together
        return self
```

## Pydantic v2 Features

### Schema Modes
```python
from pydantic import BaseModel

class User(BaseModel):
    model_config = {
        # Choose validation strictness mode
        'strict': False,  # Coerce types when possible (default)
        # 'strict': True,  # Strict type checking, no coercion
    }
    id: int
    name: str
```

### RootModel
```python
from pydantic import RootModel
from typing import List, Dict

# For when your model is just a container for a single value
IntList = RootModel[List[int]]
numbers = IntList([1, 2, 3])
print(numbers.root)  # [1, 2, 3]
print(numbers.model_dump())  # [1, 2, 3]

# For mapping types
UserDict = RootModel[Dict[str, str]]
users = UserDict({"admin": "John", "user1": "Jane"})
```

### Type Adapters
```python
from pydantic import TypeAdapter
from typing import List

# Validate without creating a model class
IntListValidator = TypeAdapter(List[int])
validated = IntListValidator.validate_python(["1", "2", "3"])  # [1, 2, 3]

# JSON parsing
json_data = '[1, 2, "3"]'
validated_json = IntListValidator.validate_json(json_data)
```

## Testing with Pydantic

### Schema Tests
```python
from pydantic import BaseModel, Field
import pytest

class Product(BaseModel):
    id: int
    name: str = Field(..., min_length=3)
    price: float = Field(..., gt=0)

def test_valid_product():
    product = Product(id=1, name="Test Product", price=19.99)
    assert product.id == 1
    assert product.name == "Test Product"
    assert product.price == 19.99

def test_invalid_product():
    with pytest.raises(ValueError):
        Product(id=1, name="TS", price=19.99)  # Name too short
    
    with pytest.raises(ValueError):
        Product(id=1, name="Test Product", price=-5)  # Negative price
```

### Pytest
Pytest is a robust testing framework for Python known for its  simple syntax, scalability, and powerful features like fixtures, parameterization, and plugins.

In order to install pytest we can just use the pip package manager and run the following command
```shell
pip install pytest
```

The execution of all pytest components can be done by running the following command
```shell
pytest
```
Alternatively, one specifiy test modules can be run
```shell
pytest test_file.py
```
Using the verbose flag we can give more output information
```shell
pytest -v
```

The basic concept for discovering the relevant test components is to identify the filenames that start with ```test_``` or end with ```_test.py```. 
The assert statement can be used to verify expressions in the pytest components.

A simple pytest defined in a test module with name ```test_component.py``` is given below
```python
import pytest

def test_component():
    assert 1 + 1 == 2
```

Tests can also be grouped within classes
```python
import pytest

class TestMathOperations:
    def test_addition(self):
        assert 1 + 2 == 2
    def test_subtraction(self):
        assert 2 - 1 == 1
```

Fixtures provide setup and teardown code for tests. They enhance test modularity and reusability.

```python
import pytest

@pytest.fixture
def sample_data():
    return {"key": "value"}
```

## Standard Library

### Unittest

### Regular expressions
The Python ```re``` package is used for working with regular expressions (regex). In particular, this allows to match, search, and manipulate
strings based on patterns

Overview of most frequently used functions
```python
match = re.match(pattern, string, flags=0)                          # re.match(r'hello', "hello world"), use match.group()
match = re.search(pattern, string, flags=0)                         # re.search(r'world', "hello world"), use match.group()
matches = re.findall(pattern, string, flags=0)                      # re.findall(r'\d+', "123 apples and 456 oranges"), gives ['123', '456']
matches = re.finditer(pattern, string, flags=0)                     # re.finditer(r'\d+', "123 apples and 456 oranges")
result = re.split(pattern, string, maxsplit=0, flags=0)             # re.split(r'[,\s]+', "apple, orange  banana")
result = re.sub(pattern, repl, string, count=0, flags=0)            # 
result, num_subs = re.subn(pattern, repl, string, count=0, flags=0) # re.subn(r'\d+', '###', "123 apples and 456 oranges")
match = re.fullmatch(pattern, string, flags=0)                      # re.fullmatch(r'\d+', "12345")
pattern = re.compile(pattern, flags=0)                              # re.compile(r'\d+'), use pattern.findall("my text")
```

#### Match 
The match function can be used as follows
```python
re.match(pattern, string, flags=0)
```

Example code
```python
import re

pattern = r'hello'
string = "hello World"

match = re.match(pattern, string)
if match:
    print("Match found: ", match.group())
else:
    print("No match found")
```


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

### Logging
The basic usage for logging message by using the default logging instance is given as follows
```Python
import logging

logging.info("This is an info message")
logging.debug('This message is for debugging purposes')
logging.warning("This is a warning message")
logging.error('This is an error message')
```
We list the different logging levels in the following
```Python
logging.DEBUG           # Detailed information, typically of interest only when diagnosing problems
logging.INFO            # Confirmation that things are working as expected
logging.WARNING         # An indication that something unexpected happened, or indicative of some problem in the near future
logging.ERROR           # Due to a more serious problem, the software has not been able to perform some function
logging.CRITICAL        # A serious error, indicating that the program itself may be unable to continue running
``` 
For logging to a specified logfile we can use
```Python
import logging

logging.basicConfig(filename='logfile-example.log', encoding='utf-8', level=logging.DEBUG)
```
By default all messages are appended to the specified logfile. In order to create a new logfile for each run we can use
```Python
logging.basicConfig(filename='logfile-example.log', filemode='w', level=logging.DEBUG)
```
For extended logging messages we can include a timestamp as follows
```Python
import logging

logging.basicConfig(filename="example2.log", 
                    format='%(asctime)s, %(levelname)s, %(message)s', 
                    datefmt='%m-%d-%Y-%H-%M-%S', 
                    level=logging.DEBUG, 
                    filemode="w")
```
### Command Line Arguments
We start with the basic setup of the argparse package
```Python
import argparse
# Create argparse object
parser = argparse.ArgumentParser()                  # Create argparse object
# Add arguments
parser.add_argument("path")                         # Add argument for parsing input parameters
parser.add_argument("file", help="file to read")    # Add help message for the given parameter
parser.add_argument("num", help"Number", type=int)  # Add argument with specified type (default: str)  
# Receive parameters      
args = parser.parse_args()                          # Parse arguments
# Evaluate parameters
print(args.path)
print(args.file)
```
This can be executed by using the command line (e.g. Bash)
```Shell
$ python main.py --help                 # Print information and usage message
```


### Database Connection


#### SQLite


### Graphical User Interfaces


#### Tkinter


## References
- Python Software Foundation: [https://www.python.org/](https://www.python.org/)
- Python Tutorial: [https://docs.python.org/3/tutorial/index.html](https://docs.python.org/3/tutorial/index.html)
- Python Standard Library: [https://docs.python.org/3/library/index.html](https://docs.python.org/3/library/index.html)
