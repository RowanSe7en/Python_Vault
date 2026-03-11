# Python Notes

---

## Printing & Variables

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

## 30 - String Formatting

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

## 1 - Python Data Types

Python data types include integers, floating-point numbers, strings, and Booleans, each serving a distinct purpose in programming.

- **Integers** represent whole numbers without decimal points.
- **Floating-point numbers** handle decimal values.
- **Strings (`str`)** are sequences of characters, defined using single (`' '`) or double quotes (`" "`), or spanning multiple lines with triple quotes.
- **Booleans** represent true or false values — most values evaluate to `True` unless they are empty or zero.

Additionally, **multiple assignment** allows assigning values to multiple variables in a single line. The `end=""` parameter in `print()` enables chaining multiple print statements on the same line.

### (*1) Integers & Floats

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

### (*2) Strings

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

### (*3) Booleans

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

### (*4) Multiple Assignment & `end=""`

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

## 3 - String Methods

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

## 7 - List

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

### List Memory Model

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

## 7-B - 2D List

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

## 8 - Tuple

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

### Tuple Memory Model

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

### Tuple Immutability vs. Rebinding

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

## 9 - Set

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

### Set Intersection — Three Ways

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

### Why `dict` Can Be Nested but `set` Cannot (and Why `frozenset` Fixes It)

A `frozenset` is hashable because it is **immutable**, whereas a regular `set` is mutable and therefore **unhashable**. Hash-based structures require stable hash values. Since a normal `set` can be modified, its hash would change, corrupting the hash table. `frozenset` is an immutable snapshot, so Python can compute a stable hash from its elements.

Dictionaries allow sets as **values** (not keys) because only keys must be hashable. Values are not used to determine storage location.

---

## 10 - Dictionary

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

## 11 - User Input

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

## 12 - Math Functions

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

## Slicing and Indexing

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

## 22 - Escape Characters

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

### ASCII Reference Table

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

## If Statement

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

### Nested If

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

## While Loop

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

## For Loop

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

## Control Flow Statements

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

## 24 - Function Definition

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
