# Python
---

## 1 - Printing & Variables

In Python, the `print()` function is used to display output, such as text, variables, or expressions, on the screen. You can include variables in `print()` using comma-separated values or by embedding them in formatted strings using the plus sign. Using `print(f'')` with f-strings, variables and expressions are inserted dynamically within curly braces `{}`. This approach is useful for generating readable and dynamic output, especially for multi-line text that includes variables or calculations.

```python
# Using print() for basic output
print("Hello, World!")

# Using variables
name = "Alice"
age = 25
city = "NewYork"
gender = "female"

# Using print() with variables
print("Your name is", name)               # using comma ","
print("Your age is", age, "you live in", city)  # using comma "," with multiple variables
print("Your are a " + gender)             # using plus "+"

# Using f-strings in a single-line print
print(f"Name: {name}, Age: {age}")
```

**Output:**
```
Hello, World!
Your name is Alice
Your age is 25 you live in NewYork
Your are a female
Name: Alice, Age: 25
```

---

## 2 - String Formatting

String formatting in Python allows you to create strings with placeholders that can be dynamically filled with variables or values.

- **`.format()` Method:** Use `{}` as placeholders and fill them with `.format()`. Example: `"Hello, {}!".format("World")`.
- **F-Strings:** Prefix the string with `f` and embed variables directly in `{}`. Example: `f"Hello, {name}"`.
- **Old `%` Formatting:** Use `%s` for strings, `%d` for integers, `%f` for floats, `%x` for hexadecimal. Example: `"Number: %d" % 42`.
- **Padding and Alignment:** Use `{:^10}` for centering, `{:<10}` for left-align, `{:>10}` for right-align.

```python
name = "Alice"
age = 30

# Using f-strings for concise and readable formatting
print(f"My name is {name} and I am {age} years old.")

# Using .format() with positional arguments
print("My name is {0} and I am {1} years old.".format(name, age))
print("My name is {1} and I am {0} years old. ^0^".format(name, age))

# Using .format() with named arguments
print("My name is {name} and I am {age} years old.".format(name="Joe", age=20))

# Formatting a reusable string with .format()
text = "My last name is {} and I am {} years old."
print(text.format("Joe", 20))
```

**Output:**
```
My name is Alice and I am 30 years old.
My name is 30 and I am Alice years old. ^0^
My name is Joe and I am 20 years old.
My last name is Joe and I am 20 years old.
```

```python
# Using old-style % formatting
print("My name is %s and I am %d years old." % ("Joe", 26))

# Adding padding and alignment with .format()
print("My name is {:<10} and I am {:^10} years old.".format("Joe", 26))

# Formatting numbers with .format()
num, num2 = 3.1457, 20

print("The number is: {:.3f}".format(num))   # Rounds to 3 decimal places
print("The number in binary is: {:b}".format(num2))  # Binary representation

# Hexadecimal representation
print("The number in hexadecimal is: {:x}".format(num2))
```

**Output:**
```
My name is Joe and I am 26 years old.
My name is Joe        and I am     26     years old.
The number is: 3.146
The number in binary is: 10100
The number in hexadecimal is: 14
```

---

## 3 - Python Data Types

Python data types include integers, floating-point numbers, strings, and Booleans, each serving a distinct purpose in programming.

- **Integers** represent whole numbers without decimal points.
- **Floating-point numbers** handle decimal values.
- **Strings (`str`)** are sequences of characters, defined using single (`' '`) or double quotes (`" "`), or spanning multiple lines with triple quotes.
- **Booleans** represent true or false values — most values evaluate to `True` unless they are empty or zero.

Additionally, **multiple assignment** allows assigning values to multiple variables in a single line. The `end=""` parameter in `print()` enables chaining multiple print statements on the same line.

### 3.1 Integers & Floats

```python
# Integer
age = 25

# Floating-Point Number
height = 5.8

print(f"Age + 1: {age + 1}, Height: {height}")
print(f"type of Age: {type(age)}, type of Height: {type(height)}")
```

**Output:**
```
Age + 1: 26, Height: 5.8
type of Age: <class 'int'>, type of Height: <class 'float'>
```

### 3.2 Strings

```python
# Strings
name = "Alice"           # Using double quotes
greeting = 'Hello, world!'  # Using single quotes
multiline_text = """This is
a multiline string."""

print(f"Name: {name}, Greeting: {greeting}")
print(f"Multiline Text: {multiline_text}")
```

**Output:**
```
Name: Alice, Greeting: Hello, world!
Multiline Text: This is
a multiline string.
```

### 3.3 Booleans

```python
# Booleans
is_sunny = True
is_raining = False

# Truthiness in Booleans
non_empty_string = "Hello"  # Evaluates to True
non_zero_number = 42        # Evaluates to True
non_empty_list = [1, 2, 3]  # Evaluates to True

empty_string = ""   # Evaluates to False
zero = 0            # Evaluates to False
empty_list = []     # Evaluates to False

print(f"Is it sunny? {is_sunny}, Is it raining? {is_raining}")
print(f"Non-empty string is True? {bool(non_empty_string)}")
print(f"Zero is True? {bool(zero)}, Empty list is True? {bool(empty_list)}")
```

**Output:**
```
Is it sunny? True, Is it raining? False
Non-empty string is True? True
Zero is True? False, Empty list is True? False
```

### 3.4 Multiple Assignment & `end=""`

```python
male, name, age = True, "Spongebob", 30

print(male, end=", ")
print(name, end=", ")
print(age)

patrick_age = Spongebob_age = 30

print(patrick_age, end=", ")
print(Spongebob_age)
```

**Output:**
```
True, Spongebob, 30
30, 30
```

---

## 4 - Type Casting

Type casting in Python refers to converting one data type into another using built-in functions like `int()`, `float()`, `str()`, and `bool()`. Python also performs some **implicit type conversion** (type coercion) during certain operations. **Nested typecasting** allows multiple conversions in a single expression.

```python
# Convert string to integer
string_number = "123"
print("String to Integer:", int(string_number), type(int(string_number)))

# Convert float to integer
float_number = 45.67
print("Float to Integer:", int(float_number), type(int(float_number)))

# Convert number to string
number = 99
print("Number to String:", str(number), type(str(number)))

# Convert to boolean
empty_string = ""
print("Empty String to Boolean:", bool(empty_string))

# Implicit Type Conversion
integer, floating = 5, 2.5
print("Implicit Type Conversion Result:", integer + floating, type(integer + floating))
```

**Output:**
```
String to Integer: 123 <class 'int'>
Float to Integer: 45 <class 'int'>
Number to String: 99 <class 'str'>
Empty String to Boolean: False
Implicit Type Conversion Result: 7.5 <class 'float'>
```

```python
# Nested typecasting
number = -7.2
converted_number = abs(int(round(number)))

print(converted_number)  # Output: 7
```

---

## 5 - String Methods

In Python, strings come with a variety of built-in methods accessed using the dot operator (`.`):

- `upper()` — Convert to uppercase
- `lower()` — Convert to lowercase
- `strip()` — Remove leading and trailing whitespace
- `repr()` — Returns a string with any special characters explicitly shown
- `replace()` — Substitute parts of a string
- `split()` — Divide a string into a list based on a delimiter
- `len()` — Determine the length of a string (not a method, it's a function)

For more info: [python_ref_string](https://www.w3schools.com/python/python_ref_string.asp)

```python
# Original string
text = "  Hello, Python World!  "

# String methods
upper_text    = text.upper()                    # Convert to uppercase
lower_text    = text.lower()                    # Convert to lowercase
stripped_text = text.strip()                    # Remove leading and trailing whitespace
replaced_text = text.replace("Python", "Programming")  # Replace part of the string
split_text    = text.split(",")                 # Split string into a list based on ','

# Getting the length of the string
length = len(text)  # Includes spaces

# Printing results
print("Original text:", repr(text))
print("Uppercase:", upper_text)
print("Lowercase:", lower_text)
print("Stripped text:", repr(stripped_text))
print("Replaced text:", replaced_text)
print("Split text:", split_text)
print("Length of the original text:", length)
```

**Output:**
```
Original text: '  Hello, Python World!  '
Uppercase:   HELLO, PYTHON WORLD!  
Lowercase:   hello, python world!  
Stripped text: 'Hello, Python World!'
Replaced text:   Hello, Programming World!  
Split text: ['  Hello', ' Python World!  ']
Length of the original text: 24
```

---

## 6 - List

A list in Python is an **ordered, mutable** collection that allows duplicate values. The syntax is `listName = [1, 2, 3]`.

Built-in list methods:
- `append(x)` — Adds element `x` to the end
- `extend(iterable)` — Extends the list by more than one element
- `insert(i, x)` — Adds element `x` at index `i`
- `pop(i)` — Removes the item at index `i`
- `remove(x)` — Removes element `x`
- `index(x)` — Returns the index of element `x`
- `count(x)` — Number of times `x` appears
- `reverse()` — Reverses the list in place

For more info: [python_ref_list](https://www.w3schools.com/python/python_ref_list.asp)

```python
my_list = [1, 2, 3, 4, 5]

my_list.append(6)         ; print(my_list)
my_list.extend([7, 8, 9]) ; print(my_list)
my_list.insert(0, 0)      ; print(my_list)
my_list.remove(0)         ; print(my_list)
my_list.pop(2)            ; print(my_list)
my_list.reverse()         ; print(my_list)

print(my_list.index(2))
print(my_list[2])
print(my_list[2:5])
print(my_list.count(4))

new_list = my_list + [77, 88, 99]
print(new_list)
```

**Output:**
```
[1, 2, 3, 4, 5, 6]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[1, 2, 4, 5, 6, 7, 8, 9]
[9, 8, 7, 6, 5, 4, 2, 1]
6
7
[7, 6, 5]
1
[9, 8, 7, 6, 5, 4, 2, 1, 77, 88, 99]
```

### 6.1 List Memory Model

In Python, a list variable doesn't contain the list directly — it holds a **reference (pointer)** to the list object stored in the **heap**. Each item in the list is also a reference to another object in the heap.

```
Stack                              Heap
(variable references)              (objects)
-------------------#-----------------------------------------------------------
fruits ------------>  list object
                      ├─ index 0 apple reference  -----------> "apple" object
                      └─ index 1 banana reference -----------> "banana" object
```

```python
fruits = ["apple", "banana"]

# The list has its own memory address.
# Each element inside the list also has its own separate memory address.
print("List object ID:", id(fruits))
print("Element 0 ID:", id(fruits[0]))
print("Element 1 ID:", id(fruits[1]))

# Both IDs are the same — the list stores a reference to the same object, not a copy.
x = 10
numbers_list = [x]

print("\nOriginal integer ID:", id(x))
print("Integer inside list ID:", id(numbers_list[0]))

# Both variables point to the same list object in memory.
numbers = [1, 2, 3]
alias = numbers

print("\nOriginal list ID:", id(numbers))
print("Alias list ID:", id(alias))
```

**Output:**
```
List object ID: 138798094018112
Element 0 ID: 138798094961616
Element 1 ID: 138798094961856

Original integer ID: 138798104495152
Integer inside list ID: 138798104495152

Original list ID: 138798094577472
Alias list ID: 138798094577472
```

---

### 6.2 2D List

A 2D list is a **list of lists** where each inner list represents a row and its elements represent columns, useful for matrices, grids, or tables.

```python
matrix1 = [1, 2, 3]
matrix2 = [4, 5, 6]
matrix3 = [7, 8, 9]

matrix = [matrix1, matrix2, matrix3]

print(matrix[0][0])   # First row, first column
print(matrix[2][2])   # Third row, third column

matrix[1][1] = 15
print(matrix)
```

**Output:**
```
1
9
[[1, 2, 3], [4, 15, 6], [7, 8, 9]]
```

---

## 7 - Tuple

A tuple in Python is an **ordered, immutable** collection. Unlike lists, elements cannot be changed once created. Syntax: `tupleName = (1, 2, 3)`.

```python
my_tuple = (1, 2, 3, 4, 5, 4)

print(my_tuple[0])
print(my_tuple[1:3])

print(my_tuple.index(1))
print(my_tuple.count(4))
```

**Output:**
```
1
(2, 3)
0
2
```

### 7.1 Tuple Memory Model

When a tuple is created, Python allocates memory for the tuple object itself and a fixed number of reference slots. Tuples do **not** reserve extra memory for resizing (unlike lists), making them more memory-efficient.

```
Stack (variable references)            Heap (objects)
-----------------------------------#----------------------------
fruits  --------------------------->  tuple object (size=2)
                                       │
                                       ├─ index 0 ──> string object "apple"
                                       └─ index 1 ──> string object "banana"
```

```python
fruits = ("apple", "banana")

print("Tuple ID:", id(fruits))
print("Tuple index 0 ID:", id(fruits[0]))
print("Tuple index 1 ID:", id(fruits[1]))
```

**Output:**
```
Tuple ID: 133803312696064
Tuple index 0 ID: 133803312729184
Tuple index 1 ID: 133803312728992
```

### 7.2 Tuple Immutability vs. Rebinding

Tuples are immutable — you cannot change their references. However, you can **rebind** a variable to a new tuple. Also, if a tuple contains a mutable object (like a list), that object itself can still be modified.

```python
# Tuple immutability vs variable rebinding and mutable elements

# 1 Original tuple
t = (1, 2, 3)
print("Original tuple:", t)
print("Original tuple id:", id(t))

# 2 Rebinding the variable to a new tuple
t = (1, 2, 3, 4)  # creates a new tuple, old tuple is unchanged
print("After rebinding:", t)
print("After rebinding id:", id(t))

# 3 Mutable object inside a tuple can change
t2 = ([1, 2], 3)
print("\nBefore modifying list inside tuple:", t2)
print("\nBefore modifying list inside tuple id:", id(t2))
t2[0].append(4)  # modifying the list, not the tuple itself
print("After modifying list inside tuple:", t2)
print("After modifying list inside tuple id:", id(t2))
```

**Output:**
```
Original tuple: (1, 2, 3)
Original tuple id: 140497400775808
After rebinding: (1, 2, 3, 4)
After rebinding id: 140497400801824

Before modifying list inside tuple: ([1, 2], 3)

Before modifying list inside tuple id: 140497399086528
After modifying list inside tuple: ([1, 2, 4], 3)
After modifying list inside tuple id: 140497399086528
```

---

## 8 - Set

A set in Python is an **unordered, mutable** collection that **does not allow duplicate values** (duplicates are removed automatically). Defined using `{}` or `set()`. Python also offers **`frozenset`**, which is an immutable set.

Built-in set methods:
- `add(item)`, `remove(item)`, `discard(item)`, `pop()`, `clear()`
- `update(*others)`, `union(*others)`, `intersection(*others)`
- `difference(*others)`, `symmetric_difference(other)`
- `issubset(other)`, `issuperset(other)`, `isdisjoint(other)`

For more info: [python_ref_set](https://www.w3schools.com/python/python_ref_set.asp)

```python
my_set  = {1, 2, 3, 4, 5, 5}
my_set2 = {5, 6, 7, 7, 8}

print(my_set & my_set2, end=" or "); print(my_set.intersection(my_set2))
print(my_set - my_set2, end=" or "); print(my_set.difference(my_set2))
print(my_set | my_set2, end=" or "); print(my_set.union(my_set2))

my_set.add(6) ; my_set2.remove(8)

print(my_set, end=" ") ; print(my_set2)

my_set.update(my_set2); print(my_set)

set1 = frozenset({1, 2, 3, 4}) ; print(set1)

set2 = set([1, 2, 3]) ; print(set2)
```

**Output:**
```
{5} or {5}
{1, 2, 3, 4} or {1, 2, 3, 4}
{1, 2, 3, 4, 5, 6, 7, 8} or {1, 2, 3, 4, 5, 6, 7, 8}
{1, 2, 3, 4, 5, 6} {5, 6, 7}
{1, 2, 3, 4, 5, 6, 7}
frozenset({1, 2, 3, 4})
{1, 2, 3}
```

### 8.1 Set Intersection — Three Ways

```python
s1 = {2, 5, 8}
s2 = {3, 2, 7}

# Using the instance method
s3 = s1.intersection(s2)
print(s3)   # Output: {2}

# Using the class method
s4 = set.intersection(s1, s2)
print(s4)   # Output: {2}

# Using an empty set instance
s5 = set().intersection(s1, s2)
print(s5)   # Output: set() — empty set has no common elements

# Non-empty instance
s5 = {2}.intersection(s1, s2)
```

### 8.2 Why `dict` Can Be Nested but `set` Cannot (and Why `frozenset` Fixes It)

A `frozenset` is hashable because it is **immutable**, whereas a regular `set` is mutable and therefore **unhashable**. Hash-based structures require stable hash values. Since a normal `set` can be modified, its hash would change, corrupting the hash table. `frozenset` is an immutable snapshot, so Python can compute a stable hash from its elements.

Dictionaries allow sets as **values** (not keys) because only keys must be hashable. Values are not used to determine storage location.

---

## 9 - Dictionary

A dictionary is a **mutable, unordered (before Python 3.7) / ordered (Python 3.7+)** collection of **key-value pairs**. Each key is unique. Defined using `{}` with `:` separating keys and values.

```python
my_dict = {"name": "John", "age": 30, "city": "New York"}

print(my_dict["name"], end=" / "); print(my_dict.get("age"), end=" / "); print(my_dict.get("height"))

my_dict["age"] = 31
my_dict["address"] = "123 Main Street"

del my_dict["city"]
print(my_dict)

print(my_dict.items())

print(my_dict.keys(), end=" / "); print(my_dict.values())
```

**Output:**
```
John / 30 / None
{'name': 'John', 'age': 31, 'address': '123 Main Street'}
dict_items([('name', 'John'), ('age', 31), ('address', '123 Main Street')])
dict_keys(['name', 'age', 'address']) / dict_values(['John', 31, '123 Main Street'])
```

```python
my_dict = {"name": "Alice", "age": 25, "city": "New York"}

for x in my_dict:
    print(x)   # ✅ Prints only keys: "name", "age", "city"

for x in my_dict.items():
    print(x)   # ✅ Prints key-value pairs as tuples

for x, y in my_dict:
    print(f"{x}: {y}")  # ❌ ERROR: Dictionary iteration returns only keys

for x, y in my_dict.items():
    print(f"{x}: {y}")  # ✅ Correct way to unpack and print key-value pairs
```

### How Python Creates and Accesses a Dictionary (Under the Hood)

When Python creates `dic = {"a": 1}`:

1. **Step 1:** Allocates a dictionary object in the heap. The variable `dic` in the stack stores a reference to it.
2. **Step 2:** Processes the key-value pair `"a": 1`. `"a"` is a hashable string; `1` is the value.
3. **Step 3:** Computes `hash("a")` → maps to a slot via `slot_index = hash("a") % table_size`.
4. **Step 4:** Handles **collisions** using open addressing with probing (checks equality, finds next empty slot).
5. **Step 5:** Stores references to both key and value in the hash table slot.
6. **Step 6:** The variable `dic` now points to the completed dictionary object.
7. **Step 7:** Accessing `dic["a"]` → computes hash → finds slot → confirms key equality → returns value.

```python
# Suppose table size is 5 (5 slots in the hash table)
table_size = 5

# Key we want to store
key = "a"

# Compute the hash of the key
key_hash = hash(key)

# Compute the slot index using modulo
slot_index = key_hash % table_size

print("Hash of key:", key_hash)   # Hash of key: -3795778419071198868
print("Slot index:", slot_index)  # Slot index: 2
```

### Summary of All Data Structures

```python
string = "New York"; string1 = " Paris"
list   = [1, 2, 3, 4, 5]; list1 = [6, 7, 8, 9]
tuple  = (1, 2, 3, 4, 5)
set    = {1, 2, 3, 4, 5}; set1 = {1, 2, 7, 8, 9}
dict   = {"name": "Joe", "age": 20}; dict1 = {"height": 178}

print(string[0], end=", "); print(list[1], end=", "); print(tuple[2], end=", "); print(dict["name"])
string = string + " 08"; list.append(6); set.add(10); dict["country"] = "USA"
print(string, end=", "); print(list, end=", "); print(set, end=", "); print(dict)
string = string.replace("s", ""); list.pop(0); set.remove(2); del dict["age"]
print(string, end=", "); print(list, end=", "); print(set, end=", "); print(dict)
string = string.replace("m", "b"); list[2] = 77; dict["name"] = "Toni"
print(string, end=", "); print(list, end=", "); print(dict)
string = string + string1; list2 = list + list1; set_union = set.union(set1); dict.update(dict1)
print(string, end=", "); print(list2, end=", "); print(set_union, end=", "); print(dict)
```

### Converting Between Data Structures

**List → Tuple:** Allocates a new tuple, copies references from the list. Result is immutable.

**Tuple → List:** Allocates a new list, copies references from the tuple. Result is mutable.

**List → Set:** Iterates the list, computes `hash(element)` for each item, inserts into a hash table. Duplicates are removed, order not preserved.

**Tuple → Set:** Same as List → Set. All elements must be hashable.

**Set → List / Set → Tuple:** Iterates the set's hash table, copies references. Order depends on set's iteration order.

---

## 10 - User Input

In Python, user input is collected using the built-in `input()` function, which returns input as a **string**. Type casting is often required for other data types.

```python
name = input("Enter your name: ")   # Takes user input as a string
age  = int(input("Enter your age: "))  # Converts input to an integer
print(f"Hello, {name}! You are {age} years old.")
```

**Output:**
```
Enter your name: Joe
Enter your age: 31
Hello, Joe! You are 31 years old.
```

---

## 11 - Math Functions

Python provides a `math` module with tools for mathematical operations: `math.sqrt()`, `math.ceil()`, `math.floor()`, `math.sin()`, `math.cos()`, `math.tan()`, `math.radians()`, `math.degrees()`, `math.exp()`, `math.log()`, `math.pi`, and more.

For more info: [module_math](https://www.w3schools.com/python/module_math.asp)

```python
import math

x     = 16
angle = 45

print("Square Root:", math.sqrt(x))
print("Ceiling:", math.ceil(4.3))
print("Floor:", math.floor(4.7))
print("Factorial:", math.factorial(5))
print("Sine of 45 degrees:", math.sin(math.radians(angle)))
print("Logarithm base 10 of 1000:", math.log(1000, 10))
print("Value of pi:", math.pi)
```

**Output:**
```
Square Root: 4.0
Ceiling: 5
Floor: 4
Factorial: 120
Sine of 45 degrees: 0.7071067811865476
Logarithm base 10 of 1000: 2.9999999999999996
Value of pi: 3.141592653589793
```

---

## 12 - Slicing and Indexing

**Indexing** retrieves a single element by position (starting at `0`, negative indexes count from the end). **Slicing** extracts a sub-sequence with `[start:stop:step]` (start inclusive, stop exclusive). The `slice()` method creates a reusable slice object.

```python
# Indexing examples
my_list = [10, 20, 30, 40, 50]
print(my_list[0])     # Access the first element: 10
print(my_list[-1])    # Access the last element: 50

# Slicing examples using [start:stop:step]
print(my_list[1:4])   # Get elements from index 1 to 3: [20, 30, 40]
print(my_list[:3])    # Get the first three elements: [10, 20, 30]
print(my_list[2:])    # Get elements from index 2 to the end: [30, 40, 50]
print(my_list[::2])   # Get every second element: [10, 30, 50]
print(my_list[::-1])  # Reverse the list: [50, 40, 30, 20, 10]

# Using the slice() method
sliced = slice(1, 4)          # Create a slice object for indices 1 to 3
print(my_list[sliced])        # Apply the slice: [20, 30, 40]

# Reusing the slice object
another_list = ['a', 'b', 'c', 'd', 'e']
print(another_list[sliced])   # Apply the same slice: ['b', 'c', 'd']

# Slicing with a custom step
step_slice = slice(0, None, 2)  # Slice from start to end with a step of 2
print(my_list[step_slice])      # [10, 30, 50]
```

**Output:**
```
10
50
[20, 30, 40]
[10, 20, 30]
[30, 40, 50]
[10, 30, 50]
[50, 40, 30, 20, 10]
[20, 30, 40]
['b', 'c', 'd']
[10, 30, 50]
```

---

## 13 - Escape Characters

Escape characters are special characters preceded by a backslash `\`. The `end=""` parameter in `print()` changes what is printed at the end (default is `\n`).

| Escape | Meaning         | Escape | Meaning          |
|--------|-----------------|--------|------------------|
| `\n`   | New Line        | `\\`   | Break new line   |
| `\t`   | Horizontal Tab  | `\r`   | Carriage Return  |
| `\v`   | Vertical Tab    | `\0`   | Null Value       |
| `\\`   | Back Slash      | `\nnn` | Octal value      |
| `\b`   | Backspace       | `\xhh` | Hex value        |
| `\'`   | Single quote    | `\a`   | Audible bell     |
| `\"`   | Double quote    | `\f`   | Form Feed        |

### 13.1 ASCII Reference Table

| Decimal | Octal | Hex | Binary      | Value |
|---------|-------|-----|-------------|-------|
| 065     | 101   | 41  | 0100 0001   | A     |
| 066     | 102   | 42  | 0100 0010   | B     |
| 067     | 103   | 43  | 0100 0011   | C     |
| 049     | 061   | 31  | 0011 0001   | 1     |
| 050     | 062   | 32  | 0011 0010   | 2     |
| 051     | 063   | 33  | 0011 0011   | 3     |

```python
print("hi\
world")

print("Follow me", end=" ")
print("I'm following")

print("Hello \nWorld")
print("Tab \t Separated")
print("tab \011 seperated")
print("hello hello\b world")
print("Python \r Language")

print('He\'s happy')
print("\"Joe\" is the name")
print("Path: C:\\folder\\file.txt")
print("Null Value: \0\0\0")
print("Octal Value: \101")       # A = (101)
print("Hexadecimal Value: \x41") # A = \x(41)
print("hexadecimal Unicode char(16): \u0041")   # A = \u(0041)
print("hexadecimal Unicode char(32): \U00000041") # A = \u(00000041)
print("Vertical Tab: \v")
print("Form Feed: \f")
print("Beep! \a")  # Produces an audible beep when printed
```

**Output:**
```
hi world
Follow me I'm following
Hello 
World
Tab 	 Separated
tab 	 seperated
hello hell world
 Language
He's happy
"Joe" is the name
Path: C:\folder\file.txt
Null Value: 
Octal Value: A
Hexadecimal Value: A
hexadecimal Unicode char(16): A
hexadecimal Unicode char(32): A
Vertical Tab: 
	
Form Feed: 

Beep!
```

---

## 14 - If Statement

An `if` statement executes a block of code only if a specified condition is `True`. Optional `elif` and `else` clauses handle additional conditions.

```python
if condition:
    # Code to execute if condition is True
elif another_condition:
    # Code to execute if another_condition is True
else:
    # Code to execute if none of the above are True
```

```python
number = 10

if number > 0:
    print("The number is positive.")
elif number < 0:
    print("The number is negative.")
else:
    print("The number is zero.")
```

**Output:**
```
The number is positive.
```

### 14.1 Nested If

```python
age = 20

if age >= 18:
    if age < 21:
        print("You are an adult but not old enough to drink in some countries.")
    else:
        print("You are an adult and can drink legally.")
else:
    print("You are a minor.")
```

**Output:**
```
You are an adult but not old enough to drink in some countries.
```

---

## 15 - Logical Operators

Python supports three main logical operators:

- `and` — `True` if **both** conditions are `True`
- `or` — `True` if **at least one** condition is `True`
- `not` — Reverses the logical state of a condition

```python
voltage = int(input("what the voltage value? "))
amp = int(input("what the amps value? "))

if 1 < amp < 9 and 12 <= voltage < 14:
    print("safe drive")
else:
    print("u can't drive the car now (check ur batterie)")

direction = input("right or left or none? ")
if direction == "right" or direction == "left":
    print("go back straight in the line")
else:
    print("^_^")
```

**Output:**
```
what the voltage value? 12
what the amps value? 5
safe drive
right or left or none? right
go back straight in the line
```

---

## 16 - While Loop

A `while` loop repeatedly executes a block of code as long as a condition is `True`. Useful when the number of iterations is unknown in advance.

```python
while condition:
    # Code to execute as long as the condition is True
    # (Optionally) include a mechanism to break the loop
```

```python
name = input("what's your name?: ")

while (len(name) <= 2):
    name = input("please enter your name?: ")

Number = int(input("choose your lucky number " + name + " ^_^: "))

while Number <= 5:
    print("You did choose the wrong number, You stuck in a loop! ")

while Number == 7:
    print("congrats You hit the jackpot ^o^! " * 4)

while Number > 5:
    print("You did choose the right number, congrats ^o^! ")
```

**Output:**
```
what's your name?: j
please enter your name?: joe
choose your lucky number joe ^_^: 2
You did choose the wrong number, You stuck in a loop! 
You did choose the wrong number, You stuck in a loop! 
... (infinite loop)
```

---

## 17 - For Loop

A `for` loop iterates over a sequence (list, tuple, string, or range) and executes a block for each element.

```python
for item in sequence:
    # Code to be executed for each item in the sequence
```

```python
# Iterating through a list
numbers = [1, 2, 3, 4, 5]
for num in numbers:
    print(num, end=" ")   # Prints each number in the list

print("\n")  # New line

# Iterating through a string
word = "Python"
for letter in word:
    print(letter, end=" ")  # Prints each letter in the string

print("\n")  # New line

# Using range()
for i in range(1, 6):    # Iterates from 1 to 5 (end is exclusive)
    print(i, end=" ")

print("\n")  # New line

for i in range(1, 10, 2):  # Iterates from 1 to 10 by 2 (end is exclusive)
    print(i, end=" ")
```

**Output:**
```
1 2 3 4 5 

P y t h o n 

1 2 3 4 5 

1 3 5 7 9
```

---

## 18 - Nested Loop

A nested loop is a loop inside another loop. The inner loop runs completely for each iteration of the outer loop. Commonly used for multidimensional data structures.

```python
rows   = int(input("How many rows you want?: "))
cols   = int(input("How many cols you want?: "))
symbol = input("What symbol you want?: ")

for row in range(rows):
    for col in range(cols):
        print(symbol, end="")
    print()
```

**Output:**
```
How many rows you want?: 5
How many cols you want?: 10
What symbol you want?: #
##########
##########
##########
##########
##########
```

```python
for x in range(1, 4):
    for y in range(1, 4):
        z = x * y
        print(z, end=", ")
    print()

for i in range(0, 5):
    for j in range(i + 1):
        print("@", end=" ")
    print()
```

**Output:**
```
1, 2, 3, 
2, 4, 6, 
3, 6, 9, 
@ 
@ @ 
@ @ @ 
@ @ @ @ 
@ @ @ @ @ 
```

```python
for i in range(0, 5):
    for j in range(i, 4):
        print(" ", end="   ")
    for j in range(i + 1):
        print("@", end="   ")
    for j in range(i):
        print("@", end="   ")
    print()

for x in range(1, 5):
    for y in range(x):
        print(" ", end="   ")
    for y in range(x, 5):
        print("@", end="   ")
    for y in range(x, 4):
        print("@", end="   ")
    print()
```

**Output:** (diamond pattern of `@` symbols)

---

## 19 - Control Flow Statements

- `break` — Terminates the loop immediately
- `continue` — Skips the current iteration and moves to the next
- `pass` — Placeholder that does nothing (used when a statement is syntactically required)

```python
list = [1, 2, 3, 4, 5]

for i in list:
    if i == 3:
        pass       # Placeholder
    elif i == 4:
        continue   # Skip this iteration
    elif i == 5:
        break      # Exit the loop

    print(f"The number is: {i}")
```

**Output:**
```
The number is: 1
The number is: 2
The number is: 3
```

---

## 20 - Function Definition

A function is a reusable block of code defined with the `def` keyword. The `return` statement sends the result back to the caller. Functions can have **default parameters** and **keyword arguments**.

```python
def test():
    print("Hello, world!")

test()  # Output: Hello, world!

def greet(name):
    print("Hello,", name)

greet("Alice")  # Output: Hello, Alice

def add(x, y):
    return x + y

print(add(5, 2))  # Output: 7

adding = add(1, 2)
print(adding)  # Output: 3
```

```python
def value(word = "world"):
    print("Hello,", word)

value()  # Output: Hello, world

def greet(*names):
    for name in names:
        print("Hello,", name)

greet("Alice", "Bob", "Charlie")
# Output: Hello, Alice
#         Hello, Bob
#         Hello, Charlie

def key(name, message):
    print(message, name)

key(message="Hi", name="Bob")  # Output: Hi Bob
```

---

## First-Class and Higher-Order Functions

In Python, functions are **first-class objects** — they can be assigned to variables, stored in data structures, passed as arguments, or returned from other functions.

### (*1) Assign Function to a Variable

```python
def greet(name):
    return f"Hello, {name}!"

# Assign the function to a variable
my_function = greet

# Assign the print function to a variable
write = print

# Call the function using the variable
write(my_function("Alice"))
```

**Output:**
```
Hello, Alice!
```

### (*2) Store Functions in Data Structures

```python
def func1():
    return "Function 1"

def func2():
    return "Function 2"

# Store functions in a dictionary with keys
function_dict = {'function1': func1,
                 'function2': func2}

print(function_dict['function1']())
print(function_dict['function2']())
```

**Output:**
```
Function 1
Function 2
```

### (*3) Pass Functions as Arguments

```python
def square(x):
    return x * x

def apply_function(func, value):
    return func(value)

# Passing 'square' as an argument
result = apply_function(square, 5)
print(result)  # Output: 25
```

### (*4) Return Functions from Functions

```python
def outer_function(message):
    def inner_function():
        return f"Message: {message}"
    return inner_function

# Getting a function as a return value
returned_function = outer_function("Hello, Python!")
print(returned_function())  # Output: Message: Hello, Python!
```

---

## 27 - *args

`*args` allows a function to accept any number of **positional arguments**, collected into a **tuple**.

```python
def greet_all(*args):
    for name in args:
        print(f"Hello, {name}!")

greet_all("Alice", "Bob", "Charlie")

def add_all(*args):
    return sum(args)

result = add_all(5, 10, 15, 20)
print("The sum is:", result)
```

**Output:**
```
Hello, Alice!
Hello, Bob!
Hello, Charlie!
The sum is: 50
```

---

## **kwargs

`**kwargs` allows a function to accept any number of **keyword arguments**, collected into a **dictionary**.

```python
def print_greeting(greeting, **kwargs):
    print(greeting)
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_greeting("Hello!", name="Alice", age=25, city="New York")
```

**Output:**
```
Hello!
name: Alice
age: 25
city: New York
```

---

## Variable Scope

The **scope** of a variable determines where it is accessible. Three primary types:

- **Local Scope** — Variables defined inside a function, accessible only within it. Use `global` keyword to promote to global scope.
- **Global Scope** — Variables defined outside any function, accessible throughout the code. Use `global` keyword inside a function to modify them.
- **Nonlocal Scope** — Applies to variables in a nested function's enclosing scope. Use `nonlocal` keyword to modify them.

### (*1) Local Scope

```python
def local_scope_example():
    local_var1 = 10  # Local variable
    print("Local variable:", local_var1)

    global local_var2  # Make local_var2 a global variable
    local_var2 = 20    # Local variable which is global now
    print("Local global variable:", local_var2)

local_scope_example()  # Output: Local variable: 10
                       # Output: Local global variable: 20

print(local_var2)  # Output: 20

# print(local_var1)  # This will raise an error — not accessible outside the function.
```

```python
def first_function():
    global local_var  # Make 'local_var' global
    local_var = 10
    print(f"From first_function: {local_var}")

def second_function():
    global local_var  # Declare 'local_var' as global to allow adjustments
    # Print the local 'local_var' which now is global because of line 3
    print(f"From second_function: {local_var}")
    local_var += 5  # adjust the original 'local_var' because of line 9
    print(f"From second_function after adding 5: {local_var}")

first_function()
second_function()
print(f"From outside the functions: {local_var}")
```

**Output:**
```
From first_function: 10
From second_function: 10
From second_function after adding 5: 15
From outside the functions: 15
```

### (*2) Global Scope

```python
global_var = 20  # Global variable

def modify_global():
    global global_var  # Using the global keyword to modify the global variable
    global_var += 10
    print("Modified global variable:", global_var)

modify_global()      # Output: Modified global variable: 30
print(global_var)    # Output: 30
```

### (*3) Nonlocal Scope

**Using `nonlocal`:**

```python
def outer_function():
    outer_var = 15  # The original "outer_var"

    def inner_function():
        nonlocal outer_var  # Referencing the original "outer_var"
        outer_var += 5      # Editing the original "outer_var"
        print("From inner_function:", outer_var)

    inner_function()
    print("From outer_function:", outer_var)

outer_function()
```

**Output:**
```
From inner_function: 20
From outer_function: 20
```

**Not using `nonlocal` (creates a separate local variable):**

```python
def outer_function():
    outer_var = 15  # The original "outer_var"

    def inner_function():
        outer_var = 5   # This is NOT the same as the original "outer_var"
        print("From inner_function:", outer_var)

    inner_function()
    print("From outer_function:", outer_var)

outer_function()
```

**Output:**
```
From inner_function: 5
From outer_function: 15
```

**Not using `nonlocal` — trying to modify (causes error):**

```python
def outer_function():
    outer_var = 15  # The original "outer_var"

    def inner_function():
        outer_var += 5  # Trying to edit the original "outer_var" without nonlocal
        print("From inner_function:", outer_var)

    inner_function()
    print("From outer_function:", outer_var)

outer_function()
```

**Output:**
```
UnboundLocalError: cannot access local variable 'outer_var' where it is not associated with a value
```

---

## Random Module

In Python, the `random` module allows you to generate random data for various purposes. You can create random floating-point numbers between 0 and 1 or within a specified range (e.g., a to b), generate random integers within a given range, select random elements from a list or tuple, and even shuffle the elements of a sequence.

```python
import random

# Generate a random floating-point number between 0 and 1
print("Random float between 0 and 1:", random.random())

# Generate a random floating-point number between a and b
print("Random float between 10 and 20:", random.uniform(10, 20))

# Generate a random integer between a and b (inclusive)
print("Random integer between 1 and 100:", random.randint(1, 100))

# Choose a random element from a list
fruits = ["apple", "banana", "cherry", "date"]
print("Random fruit:", random.choice(fruits))

# Select a random sample of 3 elements from a list
print("Random sample of 3 fruits:", random.sample(fruits, 3))

# Shuffle elements in a list
numbers = [1, 2, 3, 4, 5]
random.shuffle(numbers)
print("Shuffled numbers:", numbers)
```

**Output:**
```
Random float between 0 and 1: 0.32502099053747324
Random float between 10 and 20: 14.446561731013915
Random integer between 1 and 100: 75
Random fruit: cherry
Random sample of 3 fruits: ['date', 'cherry', 'banana']
Shuffled numbers: [2, 1, 4, 5, 3]
```

---

## 32 — Exception Handling

Exception handling allows you to manage errors that might occur during code execution. By employing `try`, `except`, and `finally` blocks, you can prevent your program from crashing and provide informative feedback to users.

- **`try` block** — Contains the code that might raise an exception.
- **`except` block** — Handles specific exceptions raised within the `try` block. You can have multiple `except` blocks for different exception types or use a single generic `except` block to catch any exception.
- You can manually raise an error using the `raise` keyword followed by the exception name.

```python
try:
    x = int(input("Enter a number: "))
    result = 10 / x

except ZeroDivisionError:
    print("Cannot divide by zero")

except ValueError:
    print("Invalid input. Please enter a valid number.")

except Exception as e:
    print("Exception occurred:", e)

else:
    print(result)

finally:
    print("Exiting try-except block")
```

**Output (example — invalid input):**
```
Enter a number: g
Invalid input. Please enter a valid number.
Exiting try-except block
```

### Raise Example

```python
def check_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative!")
    elif age < 18:
        raise PermissionError("You must be 18 or older to proceed.")
    else:
        return "Access granted."

try:
    print(check_age(-5))  # Raises ValueError

except ValueError as ve:
    print("ValueError:", ve)

except PermissionError as pe:
    print("PermissionError:", pe)
```

**Output:**
```
ValueError: Age cannot be negative!
```

### Exception Handling with a Loop

```python
number = input("Enter a number: ")

while True:
    try:
        print(10 / int(number))

    except ZeroDivisionError:
        number = input("You can't divide by zero, enter a valid number: ")

    except ValueError:
        number = input("You should enter numbers only: ")

    else:
        break
```

**Output:**
```
Enter a number: @
You can't divide by zero, enter a valid number: m
You should enter numbers only: 2
5.0
```

---

## 33 — File Detection

File detection in Python involves checking whether a file exists in the filesystem, verifying its attributes, and determining its type.

Using the `os.path` or `pathlib` modules:
- `exists()` — Check if a file exists.
- `isfile()` / `isdir()` — Check if a path is a file or directory.
- `os.stat()` — Get file attributes such as size, permissions, and modification time.

```python
import os

the_path = "Example.txt"

if os.path.exists(the_path):
    print(f"The file \"{the_path}\" exists")

print(f"Is the {the_path} a file?: {os.path.isfile(the_path)}")
print(f"The size is: {os.stat(the_path).st_size} bytes")
print(f"The file infos are: {os.stat(the_path)}")
```

**Output:**
```
The file "Example.txt" exists
Is the Example.txt a file?: True
The size is: 29 bytes
The file infos are: os.stat_result(st_mode=33206, st_ino=..., st_size=29, ...)
```

### Using `pathlib`

```python
from pathlib import Path

filename = Path("Example.txt")

if filename.exists():
    print(f"The file '{filename}' exists.")
else:
    print(f"The file '{filename}' does not exist.")
```

**Output:**
```
The file 'Example.txt' exists.
```

---

## 34 — Read a File

To read a file in Python, use the built-in `open()` function. The recommended way is the `with` statement — it ensures the file is automatically closed when the block exits, even if an exception occurs.

### File Open Modes

| Open Mode | Meaning |
|-----------|---------|
| `"r"` | Read (file must exist) |
| `"w"` | Write (creates or overwrites) |
| `"a"` | Append (adds to end) |
| `"x"` | Create new file (error if exists) |
| `"rb"` | Read binary |
| `"wb"` | Write binary |

```python
# Example 1: Manual open/close
file = open("Example.txt", 'r')
print(file.read())
file.close()

# Example 2: Using with statement (recommended)
try:
    with open("Example.txt", "r") as file:
        print(file.read())
except:
    print("The file doesn't exist")
```

**Output:**
```
Hello world!
Hello world!
```

### Read Examples

```python
# 1) Read entire file
with open("test.txt", "r") as f:
    data = f.read()
    print("Read entire file:")
    print(data)

# 2) Read line by line
with open("test.txt", "r") as f:
    print("\nRead line by line:")
    for line in f:
        print(line)
        break

# 3) Read only one line
with open("test.txt", "r") as f:
    line = f.readline()
    print("\nFirst line only:")
    print(line)

# 4) Read all lines into list
with open("test.txt", "r") as f:
    lines = f.readlines()
    print("\nLines list:")
    print(lines)
```

---

### `open()` — Notes

- `open()` returns a file object that wraps the OS-level file descriptor and provides methods for reading, writing, and managing the file.
- The file object buffers data; writes may not appear on disk until `.flush()` or `.close()` is called.
- The object keeps a file descriptor open at the OS level. Not closing it can cause **resource leaks**.

---

### `close()` — Notes

`close()` terminates access to a resource and releases the underlying system resources. When called on a file, it:
- Flushes any buffered data to disk.
- Invalidates the file descriptor at the OS level.
- Marks the object as closed — further read/write operations will raise an exception.

> Even though the file is closed, the Python object `f` still exists in memory with attributes like `.name`, `.mode`, `.encoding`, etc.

#### Common Bad Usage Scenarios for `close()`

1. **Exception before `close()`** — If `close()` is the last line in a `try` block and an exception is raised before it, the file stays open (resource leak).
2. **`open()` fails before assignment** — If `open()` fails and `finally` tries to call `.close()` on an undefined variable, you get an `UnboundLocalError`.
3. **Reference reassigned before closing** — If the file variable is reassigned to a new file before closing the original, the original handle is lost (resource leak).
4. **Double close** — Closing in `try` and again in `finally` without state checking is poor resource management.

```python
# Bad usage examples
file_name = "data.txt"
try:
    f = open(file_name, "w")
    f.write("Important data\n")
    result = 10 / 0  # Unexpected error — f.close() never reached
    f.close()
except Exception as e:
    print(f"Error occurred: {e}")

# ---

file_name = "nonexistent_directory/data.txt"
try:
    f = open(file_name, "r")  # This fails
    print(f.read())
except Exception as e:
    print(f"Original error: {e}")
finally:
    f.close()  # f was never assigned → UnboundLocalError

# ---

f = open("first.txt", "w")
f.write("First file content\n")
# Reassign before closing
f = open("second.txt", "w")
f.write("Second file content\n")
f.close()

# ---

file_name = "data.txt"
f = None
try:
    f = open(file_name, "w")
    f.write("Some content\n")
    f.close()  # First close
except Exception as e:
    print(f"Error: {e}")
finally:
    f.close()  # Second close — poor state management
```

#### The Correct Pattern

```
Initialize variable to None
→ Open inside try
→ Close in finally
→ Guard with: if file is not None
```

This prevents: leaks, undefined variables, double-close errors, and descriptor exhaustion.

---

### The Context Manager Protocol (`with` statement)

The “The Sacred Protocol” `with` statement uses two special methods:
- `__enter__()` — Called on entry; opens the file and returns the file object.
- `__exit__()` — Called on exit (even if an exception occurred); closes the file and handles cleanup.

**Three phases of `with open(...) as f:`:**
1. **Enter phase** — `__enter__()` is called; file is opened; object assigned to `file`.
2. **Execution phase** — Your code runs; exceptions are temporarily held.
3. **Exit phase** — `__exit__()` is called automatically; file is closed; cleanup happens; exceptions are either suppressed or propagated.

---

## 35 — Write a File

Use `open()` with mode `'w'` (overwrite) or `'a'` (append). Always use the `with` statement.

```python
# 1) Overwrite file
with open("test.txt", "w") as f:
    f.write("Hello world\n")

# 2) Append to file
with open("test.txt", "a") as f:
    f.write("New line\n")

# 3) Write multiple lines
lines = ["Hello\n", "World\n"]
with open("test.txt", "w") as f:
    f.writelines(lines)
```

**Resulting file:**
```
Hello world
New line
Hello
World
```

### Overwrite Example

```python
with open('Example.txt', 'w') as file:  # open the file in write mode
    # Write or overwrite data to the file
    file.write("Hello, world!!!\nThis is a test file.\n"
               "Writing data to a file in Python.")
```

**File content:**
```
Hello, world!!!
This is a test file.
Writing data to a file in Python.
```

---

## `seek()` and `tell()`

`seek()` and `tell()` control and inspect the **file cursor** (file pointer) — the position index indicating where the next read/write will occur.

- `tell()` — Returns the current cursor position ("Where am I?").
- `seek(position)` — Moves the cursor to a specific byte offset from the start.
- `seek(offset, whence)` — Advanced usage in binary mode:
  - `0` = from beginning
  - `1` = from current position
  - `2` = from end of file

```python
with open("test.txt", "r") as f:
    print("Start:", f.tell())
    data = f.read(5)
    print("Read:", data)
    print("After read:", f.tell())
    f.seek(0)
    print("After seek:", f.tell())
    print("Read again:", f.read(5))
# Output:
# Start: 0
# Read: Hello
# After read: 5
# After seek: 0
# Read again: Hello
```

### `seek()` with `whence` (binary mode)

```python
with open("test.txt", "rb") as f:
    # Move to 6th byte from start
    f.seek(6, 0)  # from start
    print("From start:", f.read(5))   # b'World'

    # Move 6 bytes forward from current position
    f.seek(6, 1)  # from current
    print("From current:", f.read(3))

    # Move 7 bytes back from end
    f.seek(-7, 2)  # from end
    print("From end:", f.read())
# Output:
# From start: b'world'
# From current: b'and'
```

---

## 36 — Copy a File

### Manual Copy

```python
# Open the source file in read mode and the destination in write mode
with open("source.txt", 'r') as source, open("destination_file", 'w') as destination:
    for line in source:
        destination.write(line)
```

### Using `shutil`

```python
import shutil

# Copies only content (no metadata)
shutil.copyfile(src="source.txt", dst="destination_file1")

# Copies content + permissions
shutil.copy(src="source.txt", dst="destination_file2")

# Copies content + all metadata (timestamps, permissions)
shutil.copy2(src="source.txt", dst="destination_file3")
```

| Method | Content | Permissions | Timestamps |
|--------|---------|-------------|-----------|
| `copyfile` | ✅ | ❌ | ❌ |
| `copy` | ✅ | ✅ | ❌ |
| `copy2` | ✅ | ✅ | ✅ |

---

## 38 — Move a File

```python
import os
import shutil

# Replace/move using os (files only)
os.replace(src="source.txt", dst="destination_file1")

# Move using shutil (works for files and directories)
shutil.move(src="source.txt", dst="destination_file2")
```

---

## 39 — Delete a File

Use `os` or `shutil` depending on what you want to delete. Always check existence first.

```python
import os
import shutil

os.rmdir('empty_dir')            # Deletes an empty directory
os.remove('example_file.txt')   # Deletes a file
shutil.rmtree('example_dir')    # Deletes a directory and ALL its contents
```

---

## File Operations — Module Summary

| Action | pathlib | os | with open | shutil |
|--------|---------|----|-----------|--------|
| Detect | ✅ | ✅ (best) | | |
| Read | | | ✅ | |
| Write | | | ✅ | |
| Copy | | | ✅ | ✅ (best) |
| Move | | ✅ | | ✅ (best) |
| Delete | | ✅ | | ✅ |

---

## 40 — Module

A **module** is a Python file that contains reusable code — functions, classes, and variables — designed to organize and simplify your programs.

- **Standard** — Built-in modules like `math`, `os`.
- **Third-party** — Installed via `pip`.
- **Custom** — Created by you.

```python
# "Test1.py" file
def function(number):
    print(f"From Test{number}: {number * 10}")

function(1)  # Output: From Test1: 10
```

```python
# "Test2.py" file
import Test1

Test1.function(2)
# Output: From Test1: 10  # From running the Test1 Code
# Output: From Test2: 20  # From the current Code (Test2)
```

**Output:**
```
From Test1: 10
From Test2: 20
```

---

## 40-A — `if __name__ == "__main__"`

This conditional checks whether the script is being **run directly** or **imported as a module**.

- When run directly → `__name__` is set to `"__main__"`.
- When imported → `__name__` is set to the module's file name.

```python
# "Test1.py" file
def greet():
    print("Hello from Test1!")

if __name__ == "__main__":
    greet()
    print(f"Script is being run directly, in \"{__name__}\" file")
else:
    print(f"This Code is Imported to {__name__} file")
```

**When run directly:**
```
Hello from Test1!
Script is being run directly, in "__main__" file
```

**When imported:**
```
This Code is Imported to Test1 file
Hello from Test1!
```

---

## 41 — Object-Oriented Programming (OOP)

**OOP** is a programming paradigm that organizes code into **objects**, which combine data (attributes) and functions (methods).

- **Class** — A blueprint/template that defines the structure and behavior of objects. It specifies attributes (data/properties) and methods (functions/behaviors).
- **Object** — A specific instance of a class. Each object has a unique memory location and its own set of attribute values.

### Class Variables

Shared among **all instances** of a class. Defined outside any method. Accessed via the class name or `self`, and modified using a `@classmethod`.

### `__init__` (Constructor)

Automatically called during object creation to initialize attributes. Cannot use `return`.

### Attributes (Instance Variables)

Unique to individual objects. Initialized in `__init__` to store object-specific data. Can be modified after creation.

### Methods

Functions within a class that define behaviors. The first parameter `self` refers to the calling object.

```python
class Car:
    wheels = 4  # Class variable

    def __init__(self, make, model, year):
        self.make = make    # Instance variable
        self.model = model
        self.year = year
        self.is_car = True
        print("Object created")

    def drive(self):
        return f"The {self.make} {self.model} is now driving with {Car.wheels} wheels"

car1 = Car("Toyota", "Corolla", 2020)
car2 = Car("Honda", "Civic", 2021)

print(car2.model)     # Civic
print(car2.is_car)    # True
print(car1.drive())   # The Toyota Corolla is now driving with 4 wheels
car2.wheels = 3       # Change instance class variable value
print(car2.drive())   # The Honda Civic is now driving with 3 wheels
```

**Output:**
```
Object created
Object created
Civic
True
The Toyota Corolla is now driving with 4 wheels
The Civic is now driving with 3 / 4 wheels
```

---

### `self` — What It Is and Why It Matters

`self` refers to the **specific instance** of the object being created or modified. It allows each object to store its own attributes and access its own methods.

Without `self`, changes would apply only to temporary local variables — the object would not remember its updated values.

```python
class Plant:
    def __init__(self, name, height, age):
        self.name = name
        height = height + 10  # ❌ local only — NOT stored on object
        self.age = age
        print(f"{self.name} grew to {height}cm")

rose = Plant("rose", 25, 30)

if rose.height > 30:  # ❌ ERROR — height was never assigned to self
    print(f"{rose.name} is tall!")
```

**Output:**
```
rose grew to 35cm
AttributeError: 'Plant' object has no attribute 'height'
```

---

### How Objects Are Stored

Instance data is stored in memory using an internal dictionary (`__dict__`). When you do `self.attribute = value`, Python inserts an entry into the object's `__dict__`.

```python
class Book:
    def __init__(self, title, pages):
        self.title = title
        self.pages = pages

b = Book("Python Basics", 200)
print(b.__dict__)            # {'title': 'Python Basics', 'pages': 200}
print(b.title)               # Python Basics
print(b.__dict__['title'])   # Python Basics
```

---

### Using the Class Name Instead of `self`

Use the class name when working with **class-level data** shared by all instances.

```python
class Car:
    total = 0  # class variable (shared)

    def __init__(self):
        Car.total += 1

    def show():
        print(f"There are {Car.total} cars")

car_1 = Car()
car_2 = Car()
car_3 = Car()
Car.show()
```

**Output:**
```
There are 3 cars
```

---

## Protected Attributes

A **single underscore** prefix (e.g., `_age`) is a convention indicating the attribute is for **internal use only**. It is NOT enforced by Python — external code can still access it.

```python
class Plant:
    def __init__(self, name, age):
        self.name = name
        self._age = age   # protected attribute

    def grow(self):
        self._age += 1
        print(f"{self.name} is now {self._age} days old.")

rose = Plant("Rose", 30)
print(rose.name)    # Output: Rose
print(rose._age)    # Output: 30 (accessible but not recommended)
rose._age = 14      # This takes effect
rose.grow()         # Output: Rose is now 15 days old.
```

---

## Name Mangling

A **double underscore** prefix (e.g., `__age`) triggers **name mangling** — Python renames the attribute internally to `_ClassName__age`. This prevents direct access by the original name from outside the class.

```python
class Plant:
    def __init__(self, name, age):
        self.name = name
        self.__age = age  # double underscore

    def grow(self):
        self.__age += 1
        print(f"{self.name} is now {self.__age} days old.")

rose = Plant("Rose", 30)
# print(rose.__age)         # AttributeError
rose._Plant__age = 14       # Accessible via mangled name (not recommended)
print(rose._Plant__age)     # Output: 30
rose.grow()
```

---

## 56 — Inheritance (OOP)

**Inheritance** allows one class (child/subclass) to inherit the attributes and methods of another class (parent/superclass). The child class can extend or override the parent's behavior.

**Types of inheritance:**
- **Single** — Child inherits from one parent.
- **Multiple** — Child inherits from multiple parents.
- **Multilevel** — Chain of inheritance (A → B → C).
- **Hierarchical** — Multiple children from one parent.
- **Hybrid** — Combination of types.

```python
# Parent class
class Animal:
    def __init__(self, name):
        self.name = name
        self.animal = "Animal"

    def Animal_speak(self):
        return f"The {self.animal} makes a sound."

# Child class
class Dog(Animal):
    def Dog_speak(self):
        return f"{self.name} barks."

# Another child class
class Cat(Animal):
    def Cat_speak(self):
        return f"{self.name} meows."

dog = Dog("Buddy")
cat = Cat("Whiskers")

print(dog.Dog_speak())       # Buddy barks.
print(cat.Cat_speak())       # Whiskers meows.
print(cat.Animal_speak())    # The Animal makes a sound.
```

**Output:**
```
Buddy barks.
Whiskers meows.
The Animal makes a sound.
```

> **Note:** A child class cannot pick and choose which arguments to pass from a parent's constructor. If `super().__init__()` is called, all required parent parameters must be satisfied. To handle cases where the child only cares about some attributes, provide **default values** for unused parameters.

```python
class Parent:
    def __init__(self, name, age, role):
        self.name = name
        self.age = age
        self.role = role

class Child(Parent):
    def __init__(self, name):
        # Provide default values for other parameters
        super().__init__(name, age=0, role="unknown")
        print(f"Name: {self.name}, Age: {self.age}, Role: {self.role}")

c = Child("Alice")
```

---

## 46 — Method Chaining (OOP)

**Method chaining** (fluent interface) allows multiple methods to be called on the same object in a single line. Each method returns `self` to enable chaining.

```python
class Calculator:
    def __init__(self, value=0):
        self.value = value

    def add(self, num):
        self.value += num
        return self  # Return the object for chaining

    def multiply(self, num):
        self.value *= num
        return self

    def divide(self, num):
        if num != 0:
            self.value /= num
        return self

    def result(self):
        return self.value

calc = Calculator()
result = calc.add(10).multiply(5).divide(2).result()
print(f"Result: {result}")  # Output: Result: 25.0
```

**Output:**
```
Result: 25.0
```

> `self` is what makes method chaining work: each call receives the same object with its updated state. Without `self`, changes would only exist temporarily inside the method.

---

## 47 — The `super()` Function (OOP)

`super()` accesses methods and attributes of a **parent class** without directly naming it. Particularly useful when a child class overrides a method but still needs the parent's functionality.

> In **multiple inheritance**, `super()` follows the **MRO (Method Resolution Order)** to determine which method to call.

```python
class Parent:
    def __init__(self, name):
        self.name = name

    def greet(self):
        print(f"Hello, my name is {self.name}.")

class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)  # Call Parent's __init__
        self.age = age

    def greet(self):
        super().greet()  # Call Parent's greet
        print(f"I am {self.age} years old.")

child = Child("Alice", 12)
child.greet()
```

**Output:**
```
Hello, my name is Alice.
I am 12 years old.
```

---

## 48 — Abstract Methods (OOP)

**Abstract classes** contain one or more abstract methods (templates with no implementation). They **cannot be instantiated directly** — subclasses must provide concrete implementations.

To define an abstract class: import `ABC` from the `abc` module and use `@abstractmethod`.

```python
from abc import ABC, abstractmethod

class Shape(ABC):  # Abstract base class
    @abstractmethod
    def calculate_area(self):
        pass

class Circle(Shape):  # Subclass implementing the abstract method
    def __init__(self, radius):
        self.radius = radius

    def calculate_area(self, pi):
        return pi * (self.radius ** 2)

circle = Circle(5)
print("Circle Area:", circle.calculate_area(3.14159))

try:
    shape = Shape()  # Cannot instantiate abstract class
except Exception as e:
    print(f"Error: {e}")
```

**Output:**
```
Circle Area: 78.53975
Error: Can't instantiate abstract class Shape without an implementation for abstract method 'calculate_area'
```

### How Python Raises Errors for Abstract Base Classes

In Python, a class that inherits from ABC does not automatically raise an error when instantiated; the error occurs only if the class contains unimplemented abstract methods. When a method is decorated with `@abstractmethod`, Python marks it with `__isabstractmethod__ = True` and adds it to the class’s `__abstractmethods__` set. During instantiation, Python checks this set: if it is non-empty, the class is considered abstract, and attempting to create an instance raises a TypeError. If the class has no abstract methods, the `__abstractmethods__` set is empty, and Python allows instantiation. So, ABCs themselves are not inherently blocked from instantiation; it is the presence of abstract methods that enforces the error, ensuring that subclasses implement all required behavior before they can be instantiated.
### How Python Tracks Abstract Methods

**Definition**

In Python, when using abstract base classes from abc, every class has a `__abstractmethods__` attribute, which is a `frozenset` containing the names of abstract methods that are not yet implemented.

- If `class A(ABC)` has a **non-empty `__abstractmethods__` set**, the class is considered **abstract**, and attempting to instantiate it (`A()`) raises a `TypeError`.
    
- If `A.__abstractmethods__` is **empty**, the class is **concrete**, and `A()` can be instantiated without error.

In the other-hand for the subclasses:

- If `class B(A)` has a **non-empty `__abstractmethods__`**, it means **not all abstract methods inherited from `A` have been implemented**, so `B()` raises a `TypeError`.
    
- If `B.__abstractmethods__` is **empty**, it means **all inherited abstract methods have been implemented**, and the class can be instantiated normally.

```python
from abc import ABC, abstractmethod

# Base class with an abstract method
class Animal(ABC):

    @abstractmethod
    def make_sound(self):
        """Abstract method that must be implemented by subclasses"""
        pass

    def eat(self):
        """Normal method"""
        print("Eating food")

# Subclass implementing the abstract method
class Dog(Animal):

    def make_sound(self):
        return "Bark"

# Inspect the base class
print("Animal.__abstractmethods__:", Animal.__abstractmethods__)

# Inspect the method objects
make_sound_method = Animal.__dict__['make_sound']
eat_method = Animal.__dict__['eat']

print("Animal.make_sound.__isabstractmethod__:", getattr(make_sound_method, "__isabstractmethod__", False))
print("Animal.eat.__isabstractmethod__:", getattr(eat_method, "__isabstractmethod__", False))

# Inspect the subclass
print("Dog.__abstractmethods__:", Dog.__abstractmethods__)

# Test instantiation
# Animal()  # This would raise TypeError
dog = Dog()
print("Dog makes sound:", dog.make_sound())
```

**Output:**
```
Animal.__abstractmethods__: frozenset({'make_sound'})
Animal.make_sound.__isabstractmethod__: True
Animal.eat.__isabstractmethod__: False
Dog.__abstractmethods__: frozenset()
Dog makes sound: Bark
```

---
# What is ABCMeata

`ABCMeta` is the metaclass responsible for:

1. Detecting methods marked with `@abstractmethod`
2. Building the `__abstractmethods__` frozenset
3. Preventing instantiation of classes that still have abstract methods
## How it appears in normal code

When you write:

```python
from abc import ABC, abstractmethod

class A(ABC):

    @abstractmethod
    def f(self):
        pass
```

`ABC` is actually defined roughly like:

```python
class ABC(metaclass=ABCMeta):
    pass
```

So your class `A` is actually created like this internally:

```python
class A(metaclass=ABCMeta):
```

## What `ABCMeta` does during class creation

When Python creates the class, `ABCMeta`:

1. Scans the class dictionary
2. Finds methods decorated with `@abstractmethod`
3. Builds:

```python
__abstractmethods__ = frozenset({...})
```

Example:

```python
print(A.__abstractmethods__)
```

Output:

```
frozenset({'f'})
```

## Instantiation check

When you try to create an instance:

```python
A()
```

`ABCMeta` checks:

```python
if cls.__abstractmethods__:
    raise TypeError
```

So Python raises:

```
TypeError: Can't instantiate abstract class A with abstract method f
```

## Subclass behavior

If a subclass implements the abstract method:

```python
class B(A):
    def f(self):
        return "done"
```

Now:

```
B.__abstractmethods__ = frozenset()
```

So:

```
B()  # allowed
```

## Why `ABCMeta` exists

It provides **interface-like behavior** in Python, similar to interfaces in languages like Java.

It ensures subclasses **must implement required methods** before they can be instantiated.
## Simple mental model

```
class → created by a metaclass
ABCMeta → metaclass that enforces abstract methods
```

✅ **One-line summary**

`ABCMeta` is the metaclass that implements Python’s abstract class system by tracking abstract methods and preventing instantiation of incomplete classes.

---

## 32-A — `NotImplementedError`

`NotImplementedError` is a built-in exception that indicates a method declared in a base class has **not been implemented** by a subclass. Used as a reminder to provide the implementation.

```python
class Animal:
    def make_sound(self):
        raise NotImplementedError("Subclasses must implement make_sound method")

class Dog(Animal):
    def make_sound(self):
        return "Dog said: Woof!"

class Cat(Animal):
    pass  # Cat doesn't implement make_sound

print(Dog().make_sound())

try:
    Cat().make_sound()  # Raises NotImplementedError
except Exception as exception:
    print("Error:", exception)
```

**Output:**
```
Dog said: Woof!
Error: Subclasses must implement make_sound method
```

---

## 49 — The Class Method (OOP)

A `@classmethod` is bound to the **class itself** rather than to instances. It takes `cls` as its first parameter instead of `self`.

**Use cases:**
1. Modify shared class variables (changes apply to all instances).
2. Alternative constructors — initialize a class in different ways.

> `self` is NOT accessible inside a `@classmethod`.

### (*1) Using `@classmethod` — shared counter

```python
class Example:
    count = 0

    @classmethod
    def increment_count(cls):
        cls.count += 1
        return cls.count

print(f"count = {Example().increment_count()}")    # count = 1
print(f"count1 = {Example.increment_count()}")     # count1 = 2
print(f"count1 = {Example.increment_count()}")     # count1 = 3

example_instance2 = Example()
print(f"count2 = {example_instance2.increment_count()}")  # count2 = 4
```

### Not Using `@classmethod` — per-instance counter

```python
class Example:
    count = 0

    def increment_count(self):
        self.count += 1
        return self.count

example_instance1 = Example()
print(f"count = {Example().increment_count()}")       # count = 1
print(f"count1 = {example_instance1.increment_count()}")  # count1 = 1
print(f"count1 = {example_instance1.increment_count()}")  # count1 = 2

example_instance2 = Example()
print(f"count2 = {example_instance2.increment_count()}")  # count2 = 1
```

### (*2) Alternative Constructor

```python
class Person:
    current_year = 2000  # Class attribute

    def __init__(self, name, age):
        self.name = name
        self.age = age
        self.current_year = 2024

    @classmethod
    def from_birth_year(cls, name, age):
        current_year = 2024
        birth_year = current_year - age
        return Person(name, age, birth_year)

Person("Alice", 40, 1984)
p = Person.from_birth_year("Alice", 40)
print(p.birth_year)
```

**Output:**
```
My name is Alice, i'm 40, i was born in 1984
My name is Alice, i'm 40, i was born in 1984
1984
```

### (*3) `self` Not Accessible in `@classmethod`

```python
class Person:
    current_year = 2000

    def __init__(self, name, age):
        self.name = name
        self.age = age
        self.current_year = 2024

    @classmethod
    def from_birth_year(cls, name, birth_year):
        age = self.current_year - birth_year  # ❌ NameError
        return cls(name, age)

try:
    Person.from_birth_year(name="Alice", birth_year=1994)
except NameError:
    print("Error: name 'self' is not defined ('self' is not accessible in classmethod)")
```

**Output:**
```
Error: name 'self' is not defined ('self' is not accessible in classmethod)
```

### Why `cls` Matters (vs. Hard-coding Class Name)

Using `cls` preserves correct inheritance — without it, subclasses are forced to share the base class's state.

```python
# ❌ Hard-coded (breaks inheritance)
class Base:
    count = 0
    @classmethod
    def inc(cls):
        Base.count += 1  # hard-coded

class Child(Base):
    count = 10

Child.inc()
print(Base.count)   # 1
print(Child.count)  # 10  (unchanged!)

# ✅ Using cls (correct)
class Base:
    count = 0
    @classmethod
    def inc(cls):
        cls.count += 1  # dynamic

class Child(Base):
    count = 10

Child.inc()
print(Base.count)   # 0
print(Child.count)  # 11
```

---

## Accessing Outer Class Instance in Nested Classes

A nested class does **not** automatically have access to the enclosing outer class instance. You must **explicitly pass** the outer instance.

```python
class Garden:
    def __init__(self, owner):
        self.owner = owner

    class Plant:
        def __init__(self, outer_instance):
            self.outer = outer_instance  # store reference to outer instance

        def show_owner(self):
            print(f"The owner is {self.outer.owner}")

    def create_magic_object(self):
        self.object_in_class = self.Plant(self)
        self.object_in_class.show_owner()

object_out_class = Garden("Alice")
object_out_class.create_magic_object()
```

**`__dict__` Proof — No Automatic Link:**
```python
class Garden:
    def __init__(self, owner):
        self.owner = owner
    class Plant:
        def __init__(self):
            pass

g = Garden("Alice")
p = g.Plant()
print("Garden object dict:", g.__dict__)   # {'owner': 'Alice'}
print("Plant object dict:", p.__dict__)    # {}  ← no reference to Garden
```

**With explicit reference:**
```python
class Garden:
    def __init__(self, owner):
        self.owner = owner
    class Plant:
        def __init__(self, outer):
            self.outer = outer

g = Garden("Alice")
p = g.Plant(g)
print("I know the object where:", p.__dict__)
# Output: {'outer': <__main__.Garden object at 0x...>}
```

---

## Class Variable & Nested Class

In a **nested class**, the class name is NOT in the global namespace — it only exists within the enclosing class's namespace. Therefore, inside nested class methods, always use `cls` (not the class name directly) to access class variables.

```python
# ✅ Using cls inside nested class
class Outer:
    class Inner:
        value = 0
        @classmethod
        def set_value(cls):
            cls.value = 100

Outer.Inner.set_value()
print(Outer.Inner.value)  # 100

# ✅ Using Outer.Inner directly (also works)
class Outer:
    class Inner:
        value = 0
        @classmethod
        def set_value(cls):
            Outer.Inner.value = 100

Outer.Inner.set_value()
print(Outer.Inner.value)  # 100
```

```python
# ❌ Inner.value = 100 inside the method will FAIL
class Outer:
    class Inner:
        value = 0
        @classmethod
        def set_value(cls):
            Inner.value = 100  # NameError — 'Inner' not in global namespace
```

**For top-level classes, both work:**
```python
class A:
    x = 10

    def set_with_name(self):
        A.x = 20  # works — A is in global namespace

    @classmethod
    def set_with_cls(cls):
        cls.x = 30  # preferred — supports inheritance

A.set_with_cls()
print(A.x)  # 30
a = A()
a.set_with_name()
print(A.x)  # 20
```

---

## 50 — The Static Method (OOP)

A `@staticmethod` is defined within a class but **not tied to a specific instance or the class itself**. It cannot access `self` or `cls`. Used for utility/helper functions that are independent of class data.

```python
class Calculator:
    @staticmethod
    def add(a, b):
        return a + b

# Call directly on the class
print(Calculator.add(5, 3))  # Output: 8

# Also accessible through an instance
calc = Calculator()
print(calc.add(7, 2))  # Output: 9
```

---

## 51 — Objects as Arguments (OOP)

You can pass objects as arguments to functions, just like any other data type. You are passing a **reference** to the object.

```python
class Person:
    def __init__(self, name):
        self.name = name

def greet(person):
    # Accepts a Person object and prints a greeting
    print(f"Hello, {person.name}!")

person1 = Person("Alice")
greet(person1)  # Output: Hello, Alice!
```

---

## 52 — Calling a Method Within a Method (OOP)

Invoking one method from inside another method within the same class. Promotes code reuse and the **DRY** (Don't Repeat Yourself) principle.

```python
class MyClass:
    def method1A(self):
        return "Method 1 is called"

    def method1B(self):
        print(f"call Method 1: {self.method1A()}")  # Calling method1A inside method1B

object = MyClass()
object.method1B()
```

**Output:**
```
call Method 1: Method 1 is called
```

---

# 45 — Method Overriding / Polymorphism (OOP)

**Method overriding** is when a subclass provides its own implementation for a method already defined in its superclass, maintaining the same method signature.

**Subtype polymorphism** — objects of different subclasses can be used interchangeably through a reference to their common parent type. Python dynamically determines the correct overridden implementation at runtime.

```python
# Parent class
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        return f"{self.name} makes a sound."

# Child class overriding speak()
class Dog(Animal):
    def speak(self):
        return f"{self.name} barks."

dog = Dog("Buddy")
print(dog.speak())  # Output: Buddy barks.
```

**Output:**
```
Buddy barks.
```

### Subtype Polymorphism Example

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass

class Dog(Animal):
    def make_sound(self):
        return "Bark"

class Cat(Animal):
    def make_sound(self):
        return "Meow"

def animal_sound(animal: Animal):
    print(f"The animal says: {animal.make_sound()}")

dog = Dog()
cat = Cat()
animal_sound(dog)  # The animal says: Bark
animal_sound(cat)  # The animal says: Meow
print(dog.make_sound())  # Bark
```

---

# Dunder Methods (Magic Methods)

**Dunder methods** (double underscore methods / magic methods) are predefined methods whose names start and end with `__`. Python calls them automatically in response to built-in operations.

| Method | Triggered By | Purpose |
|--------|-------------|---------|
| `__init__(self, ...)` | `ClassName()` | Initialize object |
| `__str__(self)` | `print()`, `str()` | Human-readable string |
| `__repr__(self)` | `repr()`, interactive shell | Unambiguous debug string |
| `__add__(self, other)` | `+` operator | Addition |
| `__mul__(self, other)` | `*` operator | Multiplication |
| `__eq__(self, other)` | `==` operator | Equality check |
| `__len__(self)` | `len()` | Length |
| `__getitem__(self, key)` | `obj[key]` | Index access |
| `__call__(self, ...)` | `obj()` | Call object like a function |

```python
class Demo:
    def __init__(self, name, values):
        self.name = name
        self.values = values

    def __str__(self):
        return f"Demo object: {self.name}"

    def __repr__(self):
        return f"Demo(name='{self.name}', values={self.values})"

    def __add__(self, other):
        return self.name + other.name, self.values + other.values

    def __mul__(self, times):
        return self.name * times, self.values * times

    def __eq__(self, other):
        return self.name == other.name and self.values == other.values

    def __len__(self):
        return len(self.values)

    def __getitem__(self, index):
        return self.values[index]

    def __call__(self):
        print(f"Called object: {self.name}")

# Usage
a = Demo("A", [1, 2, 3])
b = Demo("B", [4, 5])

print(a)          # Demo object: A         (__str__)
print(repr(a))    # Demo(name='A', values=[1, 2, 3])  (__repr__)
c = a + b         # ('AB', [1, 2, 3, 4, 5])  (__add__)
print(c)
d = a * 2         # ('AA', [1, 2, 3, 1, 2, 3])  (__mul__)
print(d)
print(a == b)     # False  (__eq__)
print(len(a))     # 3      (__len__)
print(a[1])       # 2      (__getitem__)
a()               # Called object: A  (__call__)
```

**Output:**
```
Demo object: A
Demo(name='A', values=[1, 2, 3])
('AB', [1, 2, 3, 4, 5])
('AA', [1, 2, 3, 1, 2, 3])
False
3
2
Called object: A
```

---

# 54 - The Walrus Operator `:=`

The walrus operator, also known as the **assignment expression operator**, is a feature introduced in Python 3.8. It is represented by the `:=` syntax. The purpose of the walrus operator is to **assign a variable to a value as part of an expression**, typically within control flow statements or when passing arguments to functions.

```python
#1
data = [1, 2, 3, 4, 5]

while (n := len(data)) > 0:
    print(f"List length: {n}")
    data.pop()

#2
text = "Hello, World!"

if (length := len(text)) > 10:
    print(f"The text is long with {length} characters.")
```

**Output:**
```
List length: 5
List length: 4
List length: 3
List length: 2
List length: 1
The text is long with 13 characters.
```

---

# 55 - Lambda Functions

Lambda functions in Python, often referred to as **"anonymous functions"**, are small, inline functions that can have any number of parameters but only one expression. They are defined using the `lambda` keyword followed by the parameters, a colon (`:`), then the expression to be evaluated.

**Syntax:** `(lambda parameters : expression)(arguments)`

```python
add = lambda a, b: a + b
print(add(5, 3))  # Output: 8

name = lambda first_name, last_name: first_name + " " + last_name
print(name(first_name="Joe", last_name="Doe"))  # Output: Joe Doe

# Using a lambda function directly without assigning it to a variable
print((lambda x, y: x + y)(7, 5))  # Output: 12

print((lambda age: True if age < 10 else False)(9))  # Output: True
```

---

# 56 - `sorted()` and `sort()`

- **`sorted(sequence)`** — creates a **new sorted list** without modifying the original; suitable for preserving original order or sorting immutable sequences.
- **`sequence.sort()`** — sorts **in-place**, only works on lists.
- Both accept optional parameters: `reverse=True` or `key=` to define a custom sort index.

```python
#sorted()
numbers = [3, 1, 4, 1, 5, 9]
sorted_numbers = sorted(numbers)
print(sorted_numbers)  # Output: [1, 1, 3, 4, 5, 9]

words = ['apple', 'grape', 'orange']
print(sorted(words, key=len))  # Output: ['apple', 'grape', 'orange']

sorted_numbers_desc = sorted(numbers, reverse=True)
print(sorted_numbers_desc)  # Output: [9, 5, 4, 3, 1, 1]

#sort()
numbers = [3, 1, 4, 1, 5, 9]
numbers.sort()
print(numbers)  # Output: [1, 1, 3, 4, 5, 9]

words = ['apple', 'grape', 'orange']
words.sort(key=len)
print(words)  # Output: ['apple', 'grape', 'orange']

numbers.sort(reverse=True)
print(numbers)  # Output: [9, 5, 4, 3, 1, 1]
```

---

# 57 - The `map()` Function

The `map()` function applies a given function to **each item of a sequence** (list, tuple, string) and returns a new sequence with the results.

**Syntax:** `map(function, sequence)`

> Converting the result of `map()` to a list is useful because `map()` returns a **lazy iterator** — it generates values on demand and can only be traversed once. By converting it to a list you can access all results immediately, reuse the data, and use list operations. Avoid for very large datasets.

```python
def double(x):
    return x * 2

numbers = [1, 2, 3, 4, 5]
doubled_numbers = list(map(double, numbers))
print(doubled_numbers)

#2
store = [("shirt", 20.00),
         ("pants", 25.00),
         ("jacket", 50.00),
         ("socks", 10.00)]

to_euros = lambda data: (data[0], data[1] * 0.82)
store_euros = list(map(to_euros, store))
for i in store_euros:
    print(i)

#3
def capitalize_char(char):
    return char.upper()

string = "hello"
capitalized_string = list(map(capitalize_char, string))
print(capitalized_string)
```

**Output:**
```
[2, 4, 6, 8, 10]
('shirt', 16.4)
('pants', 20.5)
('jacket', 41.0)
('socks', 8.2)
['H', 'E', 'L', 'L', 'O']
```

---

# 58 - The `filter()` Function

The `filter()` function filters elements of an iterable for which a given function returns `True`.

**Syntax:** `filter(function, iterable)`

> Like `map()`, `filter()` returns a **lazy iterator**. Convert to a list or tuple for repeated access. Avoid for very large datasets.

```python
#1
numbers = [10, 20, 33, 41, 50, 62, 70, 85]

ten_base = lambda num: num % 10 == 0
print(list(filter(ten_base, numbers)))

#2
chapels = [("Alice", 22), ("Bob", 16), ("Charlie", 25), ("David", 18), ("Emily", 10)]

adult_chapels = filter(lambda x: x[1] >= 18, chapels)
adult_chapels_list = list(adult_chapels)

print(adult_chapels_list)
```

**Output:**
```
[10, 20, 50, 70]
[('Alice', 22), ('Charlie', 25), ('David', 18)]
```

---

# 59 - The `reduce()` Function

The `reduce()` function (from `functools`) **repeatedly applies a function** to elements of a sequence, cumulatively reducing it to a single value. It processes two elements at a time: starts with the first two, applies the function, then uses the result with the next element, and so on.

```python
from functools import reduce

# Example 1: Using reduce() to calculate the product of a list
numbers = [1, 2, 3, 4]
product = reduce(lambda x, y: x * y, numbers)
print("Product of numbers:", product)  # Output: 24

# Example 2: Finding the maximum value in a list
nums = [10, 20, 5, 40, 15]
max_num = reduce(lambda x, y: x if x > y else y, nums)
print("Maximum number:", max_num)  # Output: 40

# Example 3: Using an initializer
sum_with_initializer = reduce(lambda x, y: x + y, numbers, 10)
print("Sum with initializer:", sum_with_initializer)  # Output: 20

# Example 4: Define a standalone function
def multiply(x, y):
    return x * y

# Use the function with reduce
result = reduce(multiply, numbers)
print("Product of numbers:", result)  # Output: 24
```

---

# 60 - The `zip()` Function

The `zip()` function combines **multiple iterables** into a single iterable of tuples. The i-th tuple contains the i-th element from each of the input iterables.

**Syntax:** `zip(iterable1, iterable2, ...)`

> `zip()` returns a **lazy iterator**. Convert to list, tuple, or dict for reuse. Avoid for very large datasets.

```python
# Two lists to zip
names = ["Alice", "Bob", "Charlie"]
scores = [85, 90, 78]

# Zipping the lists together
zipped = zip(names, scores)

# Convert to a list of tuples
result = list(zipped)
print(result)

# Iterating through zipped pairs
for name, score in zip(names, scores):
    print(f"{name} scored {score}")
```

**Output:**
```
[('Alice', 85), ('Bob', 90), ('Charlie', 78)]
Alice scored 85
Bob scored 90
Charlie scored 78
```

---

# 61 - List Comprehensions

List comprehensions provide a **concise way to create lists** by applying an expression to each item in an iterable, with optional filtering. Also works on sets.

**Syntax:**
```
List = [ expression for item in iterable ]
List = [ expression for item in iterable if condition ]
List = [ expression_if_true if condition else expression_if_false for item in iterable ]
List = [ function(expression) for item in iterable ]
```

```python
# Squaring numbers in a range
squares = [x**2 for x in range(5)]
print(squares)

# Filtering even numbers
list = [1,2,3,4,5,6]
evens = [x for x in list if x % 2 == 0]
print(evens)

# Categorizing numbers as "Even" or "Odd"
categories = ["Even" if x % 2 == 0 else "Odd" for x in range(5)]
print(categories)

# Applying a function to numbers
def double(x):
    return x * 2

doubled = [double(x) for x in range(5)]
print(doubled)
```

**Output:**
```
[0, 1, 4, 9, 16]
[2, 4, 6]
['Even', 'Odd', 'Even', 'Odd', 'Even']
[0, 2, 4, 6, 8]
```

---

# 62 - Tuple Comprehension

Tuple comprehension uses a syntax similar to list comprehensions but **returns a generator object** — pass it to `tuple()` to get the actual tuple.

**Syntax:**
```
Tuple = tuple( expression for item in iterable )
Tuple = tuple( expression for item in iterable if condition )
Tuple = tuple( expression_if_true if condition else expression_if_false for item in iterable )
Tuple = tuple( function(expression) for item in iterable )
```

```python
# Creating a tuple of squares
squares = tuple(x**2 for x in range(5))
print(squares)  # Output: (0, 1, 4, 9, 16)

# Creating a tuple of even numbers
evens = tuple(x for x in range(10) if x % 2 == 0)
print(evens)  # Output: (0, 2, 4, 6, 8)

# Categorizing numbers as "Even" or "Odd" in a tuple
categories = tuple("Even" if x % 2 == 0 else "Odd" for x in range(5))
print(categories)  # Output: ('Even', 'Odd', 'Even', 'Odd', 'Even')

# Applying a function to numbers and storing results in a tuple
def double(x):
    return x * 2

doubled = tuple(double(x) for x in range(5))
print(doubled)  # Output: (0, 2, 4, 6, 8)
```

---

# 63 - Dictionary Comprehensions

Dictionary comprehensions provide a **concise way to create dictionaries**, optionally filtering items.

**Syntax:**
```
dictionary = {key: expression for (key, value) in iterable.items()}
dictionary = {key: expression for (key, value) in iterable.items() if conditional}
dictionary = {key: (expr_if_true if condition else expr_if_false) for (key, value) in iterable.items()}
dictionary = {key: function(value) for (key, value) in iterable.items()}
```

```python
# Creating a dictionary with squares of values
original = {'a': 2, 'b': 3, 'c': 4}
squared_dict = {key + str(value): value ** 2 for key, value in original.items()}
print(squared_dict)  # Output: {'a2': 4, 'b3': 9, 'c4': 16}

# Filtering dictionary to include only even values
filtered_dict = {key: value for key, value in original.items() if value % 2 == 0}
print(filtered_dict)  # Output: {'a': 2, 'c': 4}

# Categorizing values as "Even" or "Odd"
categorized_dict = {key: "Even" if value % 2 == 0 else "Odd" for key, value in original.items()}
print(categorized_dict)  # Output: {'a': 'Even', 'b': 'Odd', 'c': 'Even'}

# Applying a function to values in the dictionary
def double(x):
    return x * 2

doubled_dict = {key: double(value) for key, value in original.items()}
print(doubled_dict)  # Output: {'a': 4, 'b': 6, 'c': 8}
```

---

# 63 - Set Comprehensions

Set comprehensions provide a **concise way to create sets**, similar to list comprehensions. Results are unique (no duplicates).

**Syntax:**
```
new_set = {expression for item in iterable}
new_set = {expression for item in iterable if conditional}
new_set = {expr_if_true if conditional else expr_if_false for item in iterable}
new_set = {function(item) for item in iterable}
```

```python
# Original iterable
numbers = [1, 2, 3, 4, 5]

# 1 Basic set comprehension: squares
squares = {n**2 for n in numbers}
print("Squares:", squares)

# 2 Set comprehension with condition: only even numbers
even_squares = {n**2 for n in numbers if n % 2 == 0}
print("Even squares:", even_squares)

# 3 Conditional expression inside comprehension: label numbers as 'even' or 'odd'
labels = {"even" if n % 2 == 0 else "odd" for n in numbers}
print("Labels:", labels)

# 4 Apply a function inside comprehension: convert numbers to strings
str_numbers = {str(n) for n in numbers}
print("String numbers:", str_numbers)
```

---

# 64 - `enumerate()`

The `enumerate()` function adds a **counter to an iterable** and returns it as an enumerate object — very useful when you need both the index and the value.

**Syntax:** `enumerate(iterable, start=0)`
- `iterable` — the sequence to loop through
- `start` — starting index of the counter (default is `0`)

```python
fruits = ['apple', 'banana', 'cherry']
for index, fruit in enumerate(fruits, start=1):
    print(f"Index {index}: {fruit}")

fruits = ['apple', 'banana', 'cherry']
indexed_fruits = [(index, fruit) for index, fruit in enumerate(fruits)]
print(indexed_fruits)

numbers = [10, 20, 30]
enumerated_numbers = list(enumerate(numbers))
print(enumerated_numbers)
```

**Output:**
```
Index 1: apple
Index 2: banana
Index 3: cherry
[(0, 'apple'), (1, 'banana'), (2, 'cherry')]
[(0, 10), (1, 20), (2, 30)]
```

---

# `globals()`

`globals()` is used to **dynamically create global variables** (e.g. `player1`, `player2` …) and assign them values at runtime. Useful for handling multiple related variables without explicitly defining each one.

> ⚠️ This approach reduces code readability and maintainability. A **better alternative** is using **dictionaries or lists** to store dynamically created objects — keeps data organized and avoids polluting the global namespace.

```python
# Using globals() to create variables from player1 to player4
for i in range(1, 5):
    globals()[f"player{i}"] = i * 10

print("From globals():", player1)  # type: ignore

# Using dictionary data structure to create variables from player1 to player4
player = {f"player{i}": i * 100 for i in range(1, 5)}

print("From dictionary:", player)
print("From dictionary:", player["player1"])
```

**Output:**
```
From globals(): 10
From dictionary: 100
From dictionary: {'player1': 100, 'player2': 200, 'player3': 300, 'player4': 400}
```

---

# 65 - The `time` Module

The `time` module provides functions for **working with time-related operations**:
- Accessing current time or the epoch reference point
- Converting between time representations
- Formatting time values using format codes (`Y`, `M`, `D`, `H`, `M`, `S`, `DW`, `DY`, `dst`)
- Arithmetic functions like `sleep()` to pause execution

### Time Functions Reference

| What it Shows | Formula |
|---|---|
| The date since the epoch | `time.ctime(s)` |
| The seconds passed since the epoch | `time.time()` |
| Today's date | `time.ctime(time.time())` |
| The whole structure of the universal GMT time | `time.gmtime()` |
| The whole structure of the local time | `time.localtime()` |
| A readable local or GMT time | `time.strftime(format, time.localtime())` |
| A struct_time from a readable time | `time.strptime(date, format)` |
| Time from a tuple to readable format | `time.asctime(Y,M,D,H,M,S,DW,DY,dst)` |
| Seconds from epoch to the tuple's date | `time.mktime(Y,M,D,H,M,S,DW,DY,dst)` |

### Time Format Codes

| Code | Description |
|---|---|
| `%a` | Locale's abbreviated weekday name |
| `%A` | Locale's full weekday name |
| `%b` | Locale's abbreviated month name |
| `%B` | Locale's full month name |
| `%c` | Locale's appropriate date and time representation |
| `%d` | Day of the month as a decimal number [01,31] |
| `%f` | Microseconds as a decimal number [000000,999999] |
| `%H` | Hour (24-hour clock) as a decimal number [00,23] |
| `%I` | Hour (12-hour clock) as a decimal number [01,12] |
| `%j` | Day of the year as a decimal number [001,366] |
| `%m` | Month as a decimal number [01,12] |
| `%M` | Minute as a decimal number [00,59] |
| `%p` | Locale's equivalent of either AM or PM |
| `%S` | Second as a decimal number [00,61] |

```python
import time

print(time.ctime(0))               # Convert epoch time 0 to string
print(time.ctime(1000206840))      # Convert a specific epoch time to string
print(time.time())                 # Current epoch time
print(time.ctime(time.time()))     # Convert current epoch time to string

print(time.gmtime())               # UTC time as a struct_time object

local_time = time.localtime()      # Get local time
print(local_time)                  # Print local time as a struct_time object

print(time.strftime("%D %H:%M:%S", time.localtime()))   # Format local time

print(time.strptime("6, July, 2003, 5:30", "%d, %B, %Y, %H:%M"))  # Parse time

tuple_time = (2003, 7, 6, 5, 30, 0, 0, 0, 0)
print(time.asctime(tuple_time))   # Convert tuple to a readable string
print(time.mktime(tuple_time))    # Convert tuple to epoch time
```

**Output:**
```
Thu Jan  1 01:00:00 1970
Tue Sep 11 12:14:00 2001
1735488011.3033726
Sun Dec 29 17:00:11 2024
time.struct_time(tm_year=2024, tm_mon=12, tm_mday=29, tm_hour=16, tm_min=0, tm_sec=11, tm_wday=6, tm_yday=364, tm_isdst=0)
time.struct_time(tm_year=2024, tm_mon=12, tm_mday=29, tm_hour=17, tm_min=0, tm_sec=11, tm_wday=6, tm_yday=364, tm_isdst=1)
12/29/24 17:00:11
time.struct_time(tm_year=2003, tm_mon=7, tm_mday=6, tm_hour=5, tm_min=30, tm_sec=0, tm_wday=6, tm_yday=187, tm_isdst=-1)
Mon Jul  6 05:30:00 2003
1057469400.0
```

---

# 66 - CPU-Bound vs I/O-Bound Tasks

## CPU-Bound
A **CPU-bound** task requires heavy computation from the CPU (math calculations, sorting algorithms, data processing). It keeps the CPU busy and involves little waiting for external resources. Used in scientific simulations, image processing, cryptographic operations.

→ Use **multiprocessing** to leverage multi-core CPUs and achieve true parallelism.

## I/O-Bound
An **I/O-bound** task involves input/output operations (reading/writing files, network communication, database interactions). These tasks spend time **waiting** for I/O to complete rather than computing. Used in file processing, web scraping, database queries.

→ Use **threading** to overlap I/O operations. However, threading may not give significant gains because the bottleneck is I/O speed, not CPU availability.

---

# 67 - Multi-Threading

The `threading` module allows a program to perform **multiple tasks concurrently** (continues processing while waiting). Threads share the same memory space and are lighter than processes.

> ⚠️ **GIL (Global Interpreter Lock)** — allows only **one thread to execute at a time**, even on multi-core systems. This means threading doesn't fully utilize multi-core CPUs for CPU-bound tasks. For CPU-bound work, use **multiprocessing** instead.

Threads accept the `join()` method to wait for completion.

```python
import threading
import time

def eat_breakfast():
    time.sleep(3)
    print("You eat breakfast")

def drink_coffee(number):
    time.sleep(4)
    print("You drank " + number + " coffees")

def study(name):
    time.sleep(5)
    print(f"You finish studying {name}")

x = threading.Thread(target=eat_breakfast) ; x.start() ; x.join()
y = threading.Thread(target=drink_coffee, args=("2",)) ; y.start()
threading.Thread(target=study, args=("bilal",)).start()

print(threading.active_count())
print(threading.enumerate())
print(time.perf_counter())
```

```python
import threading
import time

start_time = time.perf_counter()
threads = []

def counter(seconds):
    print(f"sleep for {seconds} secs")
    time.sleep(seconds)
    print("done")

for _ in range(2):
    a = threading.Thread(target=counter, args=[3])
    a.start()
    threads.append(a)

for i in threads:
    i.join()

end_time = time.perf_counter()
print("Elapsed time:", end_time - start_time, "seconds")
```

**Output:**
```
You eat breakfast
3
[<_MainThread(MainThread, started 9680)>, <Thread(Thread-2 (drink_coffee), started 27380)>, <Thread(Thread-3 (study), started 26416)>]
2241071.7353942
You drank 2 coffees
You finish studying bilal

sleep for 3 secs
sleep for 3 secs
done
done
Elapsed time: 3.0016264002770185 seconds
```

---

# 67-A - Daemon Threads

**Daemon threads** run in the background and **do not prevent the main program from exiting**. When all non-daemon threads complete, the program exits — regardless of whether daemon threads are still running. Used for monitoring, periodic cleanup, or non-critical background operations.

```python
import time
import threading

def timer():
    count = 0
    while True:
        time.sleep(1)
        count += 1
        print(f"logged in {count} secs")

threading.Thread(target=timer, daemon=True).start()
x = input("enter x: \n")
```

**Output:**
```
enter x:
logged in 1 secs
logged in 2 secs
logged in 3 secs
...
logged in 10 secs
```
*(timer keeps running until the user provides input, then the program exits)*

---

# 68 - Multi-Processing

The `multiprocessing` module runs **multiple processes concurrently**, where each process has its **own memory space**. This bypasses the GIL, allowing Python code to run independently across multiple CPU cores.

Use for CPU-bound tasks. Accepts the `join()` method.

```python
from multiprocessing import Process, cpu_count
import time

start = time.perf_counter()

def counter(num):
    count = 0
    while count < num:
        count += 1

def main():
    print("cpu count:", cpu_count())
    a = Process(target=counter, args=(50000000,)) ; a.start()
    b = Process(target=counter, args=(50000000,)) ; b.start()
    print("processing...")
    a.join()
    b.join()
    print("Done!")
    finish = time.perf_counter()
    print("finished in:", finish - start, "seconds")

if __name__ == '__main__':
    main()
```

**Output:**
```
cpu count: 8
processing...
Done!
finished in: 1.8089666003361344 seconds
```

```python
import multiprocessing
import time

start = time.perf_counter()

def sleep(sec):
    print(f"sleep for {sec} seconds")
    time.sleep(sec)
    print(f"done sleeping for {sec} ")

if __name__ == '__main__':
    list = []
    for _ in range(50):
        a = multiprocessing.Process(target=sleep, args=[2])
        a.start()
        list.append(a)
    for i in list:
        i.join()
    finish = time.perf_counter()
    print(f"{round(finish - start, 2)} secs")
```

**Output:**
```
done sleeping for 2
done sleeping for 2
3.15 secs
```

---

# 69 - The `concurrent.futures` Module

The `concurrent.futures` module provides **`ThreadPoolExecutor`** or **`ProcessPoolExecutor`** — a high-level interface for managing a pool of threads or processes to execute tasks asynchronously.

Useful when you want to **assign different arguments to a function**.

- Use `submit(func, args)` to submit tasks to the executor
- Use `.result()` to get the return value
- You can also use `.map()` but it accepts only 2 iterables

```python
import concurrent.futures
import time

start_time = time.perf_counter()

def task(n, sec):
    print(f"Task {n} starting...")
    time.sleep(sec)  # Simulate a 2-second task
    print(f"Task {n} finished.")
    return f"Result of task {n}"

with concurrent.futures.ThreadPoolExecutor() as executor:
    future1 = executor.submit(task, 1, 3)

    for _ in range(2):
        future2 = executor.submit(task, 2, 3)

    secs = [5, 3, 1]                                          # (1)
    future3 = [executor.submit(task, 3, sec) for sec in secs]
    for i in concurrent.futures.as_completed(future3):
        print(i.result())

    print(f"Results:, {future1.result()}, {future2.result()}")

end_time = time.perf_counter()
print("Elapsed time:", end_time - start_time, "seconds")
```

```python
import concurrent.futures
import time

start_time = time.perf_counter()

def task(sec):
    print(f"Task {sec} starting...")
    time.sleep(sec)  # Simulate a 2-second task
    print(f"Task {sec} finished.")
    return f"Result of task {sec}"

with concurrent.futures.ThreadPoolExecutor() as executor:
    secs = [5, 3, 1]
    future3 = executor.map(task, secs)
    for i in future3:
        print(i)

end_time = time.perf_counter()
print("Elapsed time:", end_time - start_time, "seconds")
```

```python
import concurrent.futures
import time

def sleep(sec):
    print(f"Sleeping for {sec} seconds")
    time.sleep(sec)
    return f"Done sleeping for {sec} seconds"

if __name__ == "__main__":
    start_time = time.perf_counter()

    with concurrent.futures.ProcessPoolExecutor() as executor:
        ex1 = executor.submit(sleep, 3)

        for _ in range(10):
            ex2 = executor.submit(sleep, 2)

        futures = [executor.submit(sleep, 1) for _ in range(2)]
        for x in concurrent.futures.as_completed(futures):
            print(x.result())

        print(f" {ex1.result()} \n {ex2.result()} ")

    end_time = time.perf_counter()
    print(f"Elapsed time: {end_time - start_time} seconds")
```

---

## Comparison: Threading vs Multiprocessing vs concurrent.futures

| Feature | `threading` | `multiprocessing` | `concurrent.futures` |
|---|---|---|---|
| I/O-bound | ✅ (best) | | ✅ |
| CPU-bound | | ✅ (best) | ✅ |
| `join()` | ✅ | ✅ | |
| `for` loop | ✅ (best) | ✅ (best) | ✅ |
| Different args per task | | | ✅ 
