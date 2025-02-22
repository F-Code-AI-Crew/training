# Environment setup

- Text editor (Choose 1): [VSCode](https://code.visualstudio.com/), [Zed](https://zed.dev/)
- Package management (Choose 1): [Anaconda](https://www.anaconda.com/download/success), [Poetry](https://python-poetry.org/), [UV](https://docs.astral.sh/uv/)

# Variable

- Variables are references to objects stored in memory.
- Python is both strongly typed and dynamically typed language

```python
temp_var = 10  # an int
temp_var = "Hello, World!"  # now come a str
```

### Python Variable Name Rules:

- Must start with a letter or the underscore character
- Cannot start with a number
- Can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
- Case sensitive
- Cannot be any of the Python keywords

Convention according to [PEP8 Function and Variable names](https://peps.python.org/pep-0008/#function-and-variable-names)

>  Function names should be lowercase, with words separated by underscores as necessary to improve readability.
>
> Variable names follow the same convention as function names.
>
> mixedCase is allowed only in contexts where that’s already the prevailing style (e.g. threading.py), to retain backwards compatibility.


You can get the data type of a variable with the `type()` function  
```Python
x = 5
y = "John"
print(type(x))  # <class 'int'>
print(type(y))  # <class 'str'>
```

If you want to specify the data type of a variable, this can be done with **casting**.  
```Python
x = str(3)    # x will be '3'
y = int(3)    # y will be 3
z = float(3)  # z will be 3.0
```

# Data type
Text Type:	`str`  
Numeric Types:	`int`, `float`, `complex`  
Sequence Types:	`list`, `tuple`, `range`  
Mapping Type:	`dict`  
Set Types:	`set`, `frozenset`
Boolean Type:	`bool`
Binary Types:	`bytes`, `bytearray`, `memoryview`  

# Numeric Expressions

### Arithmetic Operators
|Operator|Name|  
|-------:|---:|
|+|Addition|    
|-|Subtraction|  
|*|Multiplication|  
|/| Division|  
|**|Power|  
|%|Remainder|   

### Comparison Operators

|Operator|Name|  
|-------:|---:|
|==|Equal|  
|!=|Not equal|  
|>|Greater than|  
|<|Less than|  
|>=|Greater than or equal to|  
|<=|Less than or equal to|

# Comment
Comments can be used to :
- Explain Python code.
- Make the code more readable.
- Prevent execution when testing code.

```python
# This is a comment

"""
This is a comment
written in
more than just one line
"""
```

[Proper use of comments](https://stackoverflow.com/questions/46381904/proper-use-of-comments)

# List

- Python `List` functions like an array, with much more power and flexibility like holding multiple types of variables, dynamic allocation, etc.

```python
["a", True, 5]
```

Lists could be created using square brackets or the `list()` constructor:

```Python
list_1 = ["apple", "banana", "cherry"]

list_2 = list((1, 5, 7, 9, 3)) 
```

To determine how many items a list has, use the `len()` function:

```Python
my_list = ["abc", 34, True, 40, "male"]

print(len(my_list))  # The result will be 5
```

List offers negative indexing to access elements from the end of a it

```Python
this_list = ["apple", "banana", "cherry"]
print(this_list[-1]) # The result will be cherry
print(this_list[-1]) # The result will be banana
```

Slicing: You can specify **a range of indexes** by specifying where to start and where to end the range.  
When specifying a range, the return value will be a new list with the specified items.

```Python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print(thislist[2:5])  # ["cherry", "orange", "kiwi"]
print(thislist[:4])  # ["apple", "banana", "cherry", "orange"]
print(thislist[3:])  # ["orange", "kiwi", "melon", "mango"]
```

### Add List Items

To add an item to the end of the list, use the `append()` method:

```Python
thislist = ["apple", "banana", "cherry"]
thislist.append("orange")
print(thislist)  # ["apple", "banana", "cherry", "orange"]
```

To insert a list item at a specified index, use the `insert()` method:

```Python
thislist = ["apple", "banana", "cherry"]
thislist.insert(1, "orange")
print(thislist)  # ["apple", "orange", "lime", "cherry"]
```

### Remove List Items

The `remove()` method removes the specified item.  
If there are more than one item with the specified value, the method removes the first occurrence.

```Python
thislist = ["apple", "banana", "cherry", "banana", "kiwi"]
thislist.remove("banana")
print(thislist)  # ["apple", "cherry", "banana", "kiwi"]
```

The `pop()` method removes the specified index.  
If you do not specify the index, the method removes the last item.

```Python
thislist = ["apple", "banana", "cherry", "orange", "kiwi"]
thislist.pop(1)
print(thislist)  # ["apple", "cherry", "orange", "kiwi"]

thislist.pop()
print(thislist)  # ["apple", "cherry", "orange"]
```

The `del` keyword also removes the specified index:

```Python
thislist = ["apple", "banana", "cherry"]
del thislist[0]
print(thislist)  # ["banana", "cherry"]
```

The `del` keyword can also delete the list completely.

```Python
thislist = ["apple", "banana", "cherry"]
del thislist
print(thislist)  # Cause an error because "thislist" is deleted.
```

The `clear()` method empties the list.  
The list still remains, but it has no content.

```Python
thislist = ["apple", "banana", "cherry"]
thislist.clear()
print(thislist)  # []
```

### Sort List

The `sort()` method that will sort the list alphanumerically and numerically, ascending, by default:

```Python
thislist = ["mango", "apple", "pineapple", "banana"]
thislist.sort()
print(thislist)  # ["apple", "banana", "manago", "pineapple"]

thatlist = [100, 50, 65, 82, 23]
thatlist.sort()
print(thatlist)  # [23, 50, 65, 82, 100]
```

To sort descending, use the keyword argument `reverse = True`:

```Python
thatlist = [100, 50, 65, 82, 23]
thatlist.sort(reverse = True)
print(thatlist)  # [100, 82, 65, 50, 23]
```

### Join Lists

There are several ways to join, or concatenate, two or more lists in Python.  
Use the `+` operator:

```Python
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]

list3 = list1 + list2
print(list3)  # ["a", "b", "c", 1, 2, 3]
```

Use the `append()` method to add all the items from list2 into list1, one by one:

```Python
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

for x in list2:
  list1.append(x)

print(list1)  # ["a", "b", "c", 1, 2, 3]
```

Use the `extend()` method to add list2 at the end of list1:

```Python
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]

list1.extend(list2)
print(list1)  # ["a", "b", "c", 1, 2, 3]
```

# Numpy, numpy array

[Numpy docs](https://numpy.org/doc/stable/)

NumPy is used to work with arrays. The array object in NumPy is called `ndarray`.

We can create a NumPy ndarray object by using the `array()` function.

```Python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])

print(arr)  # [1, 2, 3, 4, 5]
print(type(arr))  # <class 'numpy.ndarray'>
```

### Dimensions in Arrays
A dimension in arrays is one level of array depth.

- Nested array: array that have arrays as their elements.  

NumPy Arrays provides the `ndim` attribute that returns an integer that tells us how many dimensions the array have.  

**0-D array**  
0-D arrays, or Scalars, are the elements in an array. Each value in an array is a 0-D array.
```Python
arr = np.array(42)
print(arr.dim)
```

**1-D array**  
An array that has 0-D arrays as its elements is called uni-dimensional or 1-D array.  
These are the most common and basic arrays.
```Python
arr = np.array([1, 2, 3, 4, 5])
print(arr.dim)
```

**2-D array**  
An array that has 1-D arrays as its elements is called a 2-D array.  
These are often used to represent matrix or 2nd order tensors.
```Python
arr = np.array([[1, 2, 3], [4, 5, 6]])
print(arr.dim)
```

**3-D array**  
An array that has 2-D arrays (matrices) as its elements is called 3-D array.  
These are often used to represent a 3rd order tensor.
```Python
arr = np.array([[[1, 2, 3], [4, 5, 6]], [[1, 2, 3], [4, 5, 6]]])
print(arr.dim)
```

# Function

- A function is a block of code which only runs when it is called.
- You can pass data, known as parameters, into a function.
- A function can return data as a result.

In Python a function is defined using the `def` keyword.  
To call a function, use the function name followed by parenthesis:

```Python
def my_function():
  print("Hello from a function")

my_function()
```

### Parameters

- A parameter is the variable listed inside the parentheses in the function definition.  
- An argument is the value that is sent to the function when it is called.

A function must be called with the correct number of parameters.   
Meaning that if your function expects 2 parameters, you have to call the function with 2 parameters, not more, and not less.  

```Python
def my_function(name1, name2):
  print("Hello " + name1 + " and " + name2)

my_function("Bob", "Fred")  # Hello Bob and Fred
my_function("Harry")  # This will cause an error
```

You can also send arguments with the key = value syntax.  
This way the order of the arguments does not matter.

### Default Parameter Value

If we call the function without parameter, it uses the default value:

```Python
def my_function(country = "Japan"):
  print("I am from " + country)

my_function("Vietnam")
my_function()
my_function("India")
```

### Return Values

To let a function return a value, use the `return` statement:

```Python
def my_function(x):
  return 5 * x

print(my_function(3))  # 15
print(my_function(5))  # 25
```

### The pass Statement

`function` definitions cannot be empty, but if you for some reason have a `function` definition with no content, put in the `pass` statement to avoid getting an error.

```Python
def myfunction():
  pass
```

# Resources

- https://docs.python.org/3/
