<!--
.. title: python-basics
.. slug: python-basics
.. date: 2019-08-08 20:53:11 UTC+01:00
.. tags: python
.. category: python
.. link: 
.. description: 
.. type: text
.. author: Abdul Sayyed
.. summary: 
-->

[//]:# ( MOOCs stands for massive open online courses, example of MOOC platforms are Open EdX, Coursera. Canvas, Moodle and other are example of LMS {Learning management Software}. They are cloud base software platform designed to create and distribute interactive educational content. {SPOC is small private online courses}, Stepik is also a cloud based platform, a full featured MOOC, to help people for e-learning, can be integrated in LMS or MOOC-platform using Learning Tools interoperability LTI)

## An introductory book on Python by Allen [Think Python](/files/thinkpython2.pdf)

## Languages primitive data

- Variables are primitive data type in Python and are declared without any key word `num1 = 100` hence Python is said to be **dynamically implicitly typed language** because the type of the variable is defined at run time implicitly.

- There are **Built in data type**: such as *numbers { integers, floats, complex numbers}, strings, lists, tuples and dictionaries*.

## Rules for Variable names

- The only characters that are allowed are **letters**, **numbers**, and **underscores**. Also, they can't start with numbers.
- When declaring variable you don't need a var or Var like other languages, just type the name of the variable and assigned some value to it.
- x = 10 her x is a variable which is assigned 10, it can be deleted by using **del** operator.
- Many other languages have special operators such as '++' as a short cut for 'x += 1'. Python does not have these.
- If a variable is not defined  ( assigned a value) trying to use it will cause an error. ( name is not defined)
- a = b = c = 2 , her 2 is assigned to all a, b and c variable.
- To see the internal type use `print(type(a))` you should get // <class int>
- int(...), float(...), str(...) is used to cast one type to another type.
- Multiple assignment is possible as well

```py
 a,b = 10,20   # a is 10 while b is 20
 a,b = b, a+b  # a is given b's value while b is given a+b value.
 a = b = c = 2  # here 2 is assigned to all a, b and c variable.

    >>> a = 4
    >>> b = 6
    >>>
    >>> a + b
    10
    >>>
    >>> a += 2
    >>> a
    6
    >>>
    >>> a = "Python"
    >>> c = "MATLAB"
    >>> z = " > "
    >>> a + z + c
    'Python > MATLAB'
```

## Blocks in other language but indentation in Python

- Python uses indentation (white space at the beginning of a line) to delimit blocks of code. Other languages, such as C, use curly braces to accomplish this, but in Python indentation is mandatory; programs won't work without it. As you can see, the statements in the if should be indented.
- An else statement follows an if statement, and contains code that is called when the if statement evaluates to False.

- As with if statements, the code inside the block should be indented.

```py
x = 4
if x == 5:
   print("Yes")
else:
   print("No")
```

- The short cut to `else if` is `elif`, colon is must and second line must be indented as opposed to curly brackets `{`
- An if .. elfi ..elif sequence is replacement for the switch or case in other languages. Python does not have `swithc, case`.

## Boolean Logic

> **and**, **or**, **!=** , **>** and **<** and **not** operators are used

- `1 == 1 and 2 == 2`  would yield `True`. In other language instead of `and` an ampersand sign `&` is used to represent `and`.
- `not 1 == 1`, first `1==1` is executed then inverted with not.
- `if 2!=3:` is comparing `2 is not equal to 3`

### True and False

- True and False are special objects in Python. They are of type bool (for Boolean).

```py

>>>
>>> strange_election = True
>>> uncomfortable_choices = True
>>> satisfying_experience = False
>>> strange_election and uncomfortable_choices
True
>>> strange_election and satisfying_experience
False
>>> strange_election and not satisfying_experience
True
We often use these in if statements:

>>>
>>> if strange_election and not satisfying_experience:
...     print('Watching a lot of news')
Watching a lot of news

```

## operators

- **//** floor division, is used for remainder while **%** modules is used for Quotient.

## Operator Precedence or order of operations

- `==` has a higher precedence than `or`, unless specified with parenthesis.
- `False == False or True` would become `True == False` and would yield `True`.
- parentheses first, then exponentiation, then multiplication/division, and then addition/subtraction. 
- 
    1)P-Parentheses
    2)E-Exponents
    3)M-Multiplication || D-Division
    4)A-Addition || S-Subtraction

- If same precedence it is from ....
- What is the output of `-10**2`, the answer is `-100` because **has a higher precedence than -. To avoid this problem do code safely. (-10)** 2 will give the desired result

```python
()
Parentheses (grouping)

f(args...)
Function call

x[index:index]
Slicing

x[index]
Subscription

x.attribute
Attribute reference

**
Exponentiation

~x
Bitwise not, it flips the binary number so if (~2) means (~0010) would become (1101) becomes 13.

+x, -x
Positive, negative

*, /, %
Multiplication, division, remainder

+, -
Addition, subtraction

<<, >>
Bitwise shifts

&
Bitwise AND

^
Bitwise XOR

|
Bitwise OR

in, not in, is, is not, <, <=,  >,  >=,
<>, !=, ==	
Comparisons, membership, identity

not x
Boolean NOT

and
Boolean AND

or
Boolean OR

lambda
Lambda expression
```

![operator-precedence.png](/images/python/operator-precedence.jpg)

- Would you write this if `not 1 + 1 == y or x == 4 and 7 == 8:` in your code ? The answer is no, not at all because it is not clear. Though if given we can take help from precedence order but the wise thing to do is to write it with clear parentheses so when you see your own code after a month you know exactly what you want.
- All comparison operations in Python have the same priority. 
- So the better way is to write it like `not (1+1) == y or (x ==4 and 7==8)` or ((1+1) == y) or (....)` depending what is your intention.
- Coming back t precedence operator, say we need to solve the following
  - not 1 + 1 == y or x == 4 and 7 == 8
  - Step 1: question  to ask which operator has precedence `+, == or , and`
    - First `+` Second `==`, third not fourth `and` fifth `or`.  according to [data-flair](https://data-flair.training/blogs/python-operator-precedence/)


```py
x =4, y=2
First step: 1 +1 --> not 2 ==y or x ==4 and 7 ==8
Second step: 2 == y == --> not True or True and False
Third step: not --> False or True and False
Fourth step: and ---> False or False --> False
```

## While Loops

- While loop runs forever if condition is true, it is like if statement but if only run once.
- in while loop break breaks the loop while continue stop execution and go back to the beginning of while loop.
- while statements are another example with an initial test followed by an indented block. Here’s an example where we find the largest Fibonacci number less than 1000:


>Note: in any loop when you use print() command it automatically print a new line, to avoid this behaviour an keyword `end` can be used as shown below:

```py
>>> a, b = 0, 1
>>> while a < 1000:
...     print(a, end=',')
...     a, b = b, a+b
...
0,1,1,2,3,5,8,13,21,34,55,89,144,233,377,610,987,
---

- Notice the initial while test: while fibonacci < 1000:, followed by the indented while block. Unlike the if statement, Python will continue to run the statements in the while block until the conditional in the while test evaluates to False.

```py
>>>
>>> last_but_1 = 0
>>> fibonacci = 1
>>> while fibonacci < 1000:
...     last_but_2 = last_but_1
...     last_but_1 = fibonacci
...     fibonacci = last_but_2 + last_but_1
>>> print("Largest Fibonacci < 1000 is", last_but_1)
Largest Fibonacci < 1000 is 987
```

- A `pass` statement can be used if programe requries no action but it is needed for some purpose for example you want to include some logic in future but can not come up with something, so you are saying let it go as it is now we will see what to put here.

```py
def initlog(*args):
    pass   # Remember to implement this!

class MyClass:
    pass
```


## Types

- To see the internal type use `print(type(a))` you should get `<class int>`
- `int(...), float(...), str(...)` is used to cast one type to another type.

## Augmented Assignment

- Augmented assignment is a single statement combining a binary operation and an assignment statement such as `+=, -=,` etc.


## Strings

- Concatinaiton : +
- Multiplication : * how many times you want that string to be printed
- indexing : string indexing starts with [0], so if `name = "Sayyed"` then name[2] would yield `y`
- negative indexing : name[-1] would give the last letter in a string
- Slicing: To get the multiple charachter from a string called slicing: name[1:4] would yield Sayyed because a being 1 while e being at index 4,

```
//str[start:end] # items start through end-1
//str[start:]    # items start through the rest of the array
//str[:end]      # items from the beginning through end-1
//str[:]   
```

- `in` Operator
- String length
- Character escaping: `\' or \" or \`
- Basic string method: `upper and lower`
- String formatting: it is taken from c language, it is used to combine a string with another variable without using + as in call

```py
x = "tem's 10 dollara!"

print("Hello it is me! %s" %x) // in place of %s the value of x will be printed, for decimal and numerical %d is used

subject = "English"
name = "John"

print("This is my %s and I like %s , %(subject,name)) // will replace the variable

```

### Strings can have quotes or double quotes, there’s no difference in Python:

```py
    >>>
    >>> first = 'a string'
    >>> second = "b string"
    >>> first + second
    'a stringb string'
    Length of a string:
    >>>
    >>> len(first)
    8
```

### Strings and numbers are different:

```py
    >>>
    >>> number = "9"
    >>> number + 6
    Traceback (most recent call last):
       ...
    TypeError: cannot concatenate 'str' and 'int' objects
```

### We can convert between numbers and strings:

```py
    >>>
    >>> int(number) + 6
    15
    >>> str(9)
    '9'
    However...
>>>
>>> number = "nine"
>>> int(number)
Traceback (most recent call last):
...
ValueError: invalid literal for int() with base 10: 'nine'
```

### Strings are sequences


```py
>>>
>>> # Raises a TypeError
>>> # my_string[1] = 'N'
Adding strings
>>>
>>> my_string + ' with added insight'
'interesting text with added insight'
```

- Like lists, strings are sequences (have length, can be iterated, can index, can slice).

```py 
>>>
>>> # Length
>>> len(my_string)
16
>>>
>>> # Iterable
>>> for c in my_string:
...     print(c)
i
n
t
e
r
e
s
t
i
n
g

t
e
x
t
```

### String methods

- Strings have lots of interesting methods. In IPython, try tab-complete on a string variable name, followed by a period – e.g. type my_string., followed by the tab key. See also the list of string methods in the Python docs.

- One interesting method is replace. It returns a new string that is a copy of the input, but replacing instances of one string with another:

```py
>>>
>>> another_string = my_string.replace('interesting', 'extraordinary')
>>> another_string
'extraordinary text'
```

- Notice that the original string has not changed (it’s immutable):

```py
>>>
>>> my_string
'interesting text'
```

- Use the split method to break a string into a list of strings. By default, split will split the string at any white space (spaces, tab characters or line breaks):

```py
>>>
>>> my_string.split()
['interesting', 'text']
Pass a character to split to split the string at that character:
>>>
>>> another_example = 'one:two:three'
>>> another_example.split(":")
['one', 'two', 'three']
```

- The strip method returns a new string with spaces, tabs and end of line characters removed from the beginning and end of the string:

```py
>>>
>>> # A string with a newline character at the end
>>> my_string = ' a string\n'
>>> my_string
' a string\n'
>>> my_string.strip()
'a string'
```

- Inserting values into strings
- See: Inserting values into strings.

### String formatting

- To combine strins and non strings you have converted the non strings to strings
- String formatting provides a more powerful way to embed non-strings within strings. String formatting uses a string's format method to substitute a number of arguments in the string.

```py

# string formatting
nums = [4, 5, 6]
msg = "Numbers: {0} {1} {2}". format(nums[0], nums[1], nums[2])
print(msg)
print("{0}{1}{0}".format("abra", "cad")) # abracadabra
```

### String useful function

```
print(min(1, 2, 3, 4, 0, 2, 1))
print(max([1, 4, 9, 2, 5, 6, 8]))
print(abs(-99))
print(abs(42))
print(sum([1, 2, 3, 4, 5]))
```

- More string

```py
>>>
>>> example = "mary had a little lamb"
>>> print(example)
mary had a little lamb
String slicing:
>>>
>>> example[0]
'm'
>>>
>>> example[0:4]
'mary'
You can split strings with any character. This breaks up the string, returning a list of strings broken at the separator character:
>>>
>>> example.split(" ")
['mary', 'had', 'a', 'little', 'lamb']
>>>
>>> example.split(" ")[4]
'lamb'
You can split with any character:

>>>
>>> another_example = 'one:two:three'
>>> another_example.split(":")
['one', 'two', 'three']
You can also strip a string. That returns a new string with spaces, tabs and end of line characters removed from the beginning and end:

>>>
>>> my_string = ' a string\n'
>>> my_string
' a string\n'
>>> my_string.strip()
'a string'
Adding strings:

>>>
>>> example + " or two"
'mary had a little lamb or two'
Puting strings into other strings:

>>>
>>> subject_id = "sub1"
>>> print("Subject {} is excellent".format(subject_id))
Subject sub1 is excellent
>>>
>>> age = 29
>>> print("Subject {} is {} years old".format(subject_id, age))
Subject sub1 is 29 years old
You can do more complex formatting of numbers and strings using formatting options after a : in the placeholder for the string. See: https://docs.python.org/3.5/library/string.html#format-examples.

>>>
>>> print("Subject {:02d} is here".format(4))
Subject 04 is here
```

## String formatting when printing taken from C

```py
x = "tem's 10 dollara!

print("Hello it is me! %s" % x) // in place of %s the value of x will be printed, for decimal and numerical %d is used

subject = "English"
name = "John"

print("This is my %s and I like %s , %(subject,name)) // will replace the variable

```


## Built in Data Structure

- **List** are enclosesd in square brackets `l=[1,2,"Three"]` and ordered sequences of objects
- **Tuple** are enclosed in parenthesis `t=(1,2,"Three")`, they are also ordered objects but are faster than list and can not be changed thus called `immutables`
- **Dicts** are enclosed in curly brackets `d={"a":1, "b":2}
- **Strings** are enclosed in single or double quotation marks,can contain only chrarcters and are built using the `set()` built in function.
- **Sets** are constuected from unique objects as they can not be duplictated `s1=set_a([1,2,3,4])` and `s2=set_b([2,3,4,5,6])` then `s1 | s2` would yield {1,2,3,4,5,6}. They are mutable.
  - Union `s1 |s2`
  - Intersection `s1 & s2`
  - Subset `s1 < s2` # False or True
  - Difference `s1 - s2` # {1}
  - Symmetric Difference `s1 ^ s2` # {1,5,6}

- **Frozensets**

### Lists are mutable in python that is they can be changed using index or can be appended

- Array are called list in Python which is not an intelligent thing to do. They are also object and used to store an indexed items in indexed list using square brackets with commas.. Same as in array its index starts with zero.
- Unlike other languages Python list can be nested and can store heterogeneous data. `things = ["Hello",90,[2.3, 56], 3.89]. To get to the inside list need to use two brackets. things[2][0] should give 2.3
- Lists can be added ( concatinated / inserted) and multiplied in the same way as strings.
- To check if an item is in a list, the `in` operator can be used. It returns True if the item occurs one or more times in the list, and False if it doesn't.
- Note that the append method does not return the list, it just changes the list in-place. Python returns None from the append method:

```python
words = ["spam", "egg", "spam", "sausage"]
print("spam" in words)
print("egg" in words)
print("tomato" in words)
```

- A Python list is like a cell array in MATLAB, or a list in R.
- To check if an item is not in a list, you can use the not operator in one of the following ways:

```python
nums = [1, 2, 3]
print(not 4 in nums)
print(4 not in nums)
// The above both are same
print(not 3 in nums)
print(3 not in nums)
```

- Appending list item using `append` method, while `len` gives the length of an array but it is not a method but a built in function

```python
numbers = [1,2,3]
numbers.append(4)
print(numbers) // [1,2,3,4]
print(len(numbers)) // 4
animals = ['elephant', 'lion', 'tiger', "giraffe"]  # create new list
print(animals)

animals += ["monkey", 'dog']    # add two items to the list
print(animals)
```

- The insert method is similar to append, except that it allows you to insert a new item at any position in the list, as opposed to just at the end.

```python
words = ["Python", "is", "fun", 1]
index = 3
words.insert(index,"!")
print(words) // []

animals = ['elephant', 'lion', 'tiger', "giraffe", "monkey", 'dog']   # create new list
print(animals)

animals[1:3] = ['cat']    # replace 2 items -- 'lion' and 'tiger' with one item -- 'cat'
print(animals)

animals[1:3] = []     # remove 2 items -- 'cat' and 'giraffe' from the list
print(animals)

animals= []  # List is empty now
print(animals)
```

- The `index` method finds the first occurrence of a list item and returns its index.
- If the item isn't in the list, it raises a ValueError.
- List slices can also have a third number.

```py
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(squares[::2]) # It simply means that from the start to tthe end with 2 steps
print(squares[2:8:3])
```

```py
numbers = [12,13,14]
numbers.index(12) // should return 0
```

- A list may be reversed 

```py
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(squares[1:-1])
# to print in reverse order
print(squares[::-1])

```

- **List Comprehensions**
- List comprehensions are a useful way of quickly creating lists whose contents obey a simple rule.
For example, we can do the following:

```py 
# to print squrare from 100 numbers
squares= [i**2 for i in range(11)]
print(squares)

# To impose the condition u can use if, here only even numbers are generated.

squares = [i**2 for i in range(11) if i**2/2 == 0]
print(squares)

- This will produce a memory error if not careful `even = [2*i for i in range(10**100)]`

- The `index` method finds the first occurrence of a list item and returns its index.
-  

If the item isn't in the list, it raises a ValueError.

```py
numbers = [12,13,14]
numbers.index(12) // should return 0
```

- iterating over the list
- Python indices are 0-based
- Indices for Python sequences start at 0. For Python, the first element is at - index 0, the second element is at index 1, and so on:
- - Negative indices
- Negative numbers as indices count back from the end of the list. For example, use index -1 to return the last element in the list:

```py
>>>
>>> my_list
[9, 4, 7, 0, 8]
>>> my_list[-1]
8
```

- In Python, variable names point to an object.

- When you do another_variable = a_variable, you are telling the name another_variable to point to the same object as the name a_variable. When objects are mutable, this can be confusing:

```py
>>>
>>> another_list = my_list
>>> another_list
[9, 99, 7, 0, 8]
```

- my_list points to a list object in memory. When you do another_list 
- my_list, it tells Python that another_list points to the same object. So, if we modify the list, pointed to by my_list, we also modify the value of another_list, because my_list and another_list point at the same list.

```py
>>>
>>> my_list[1] = 101
>>> another_list
[9, 101, 7, 0, 8]
```

- This is the third from last element:

```py
>>>
>>> my_list[-3]
7
```

```py
>>> # Can be indexed
>>> my_list[1]
4
>>> # Can be sliced
>>> my_list[0:2]
[9, 4]
>>>
>>> for e in my_list:
...     print(e)
...
9
4
7
0
8
. Our Reference: 115758.002 
```


### There are a few more useful functions and methods for lists.

- max(list): Returns the list item with the maximum value
- min(list): Returns the list item with minimum value
- list.count(obj): Returns a count of how many times an item occurs in a list
- list.remove(obj): Removes an object from a list
- list.reverse(): Reverses objects in a list
- 

- The range function creates a sequential list of numbers.The code below generates a list containing all of the integers, up to 10. 

```python
list(range(10)) would result in [1,2.......10] 
print(list(range(5))) would result in [0,1,2,3,4]
square = [1,4,9,16,25]
print(squares[1:4]) // 4,9,16

```

- The reason it is converted into `list` because otherwise it is an object of not type an array but range, thus casting is necessary.

- If range is called with one argument, it produces an object with values from 0 to that argument.If it is called with two arguments, it produces values from the first to the second.


```python
print(list(range(1,4))) // [1,2,3]
similarly  range(4) and range(0,4) are equal
```

- range can have a third argument, which determines the interval of the sequence produced. This third argument must be an integer.

```python
print(numbers(list(range(10,22,2)))) would print [10,12,14......20]
```

## Tuples

- Tuples are almost identical to lists. The only significant difference between tuples and lists is that tuples cannot be changed: you cannot add, change, or delete elements from the tuple. Tuples are constructed by a comma operator enclosed in parentheses, for example (a, b, c). A single item tuple must have a trailing comma, such as (d,).


- Trying to reassign a value in a tuple causes a TypeError.
- Tuples can be created without the parentheses, by just separating the values with commas.`my_one = "1","2","3"
- An empty tuple is created using an empty parenthesis pair: `tpl = ()`
- Tuples are faster than lists, but they cannot be changed.


```py
- A tuple with two elements:

```python
>>>
>>> two_tuple = (1, 5)
>>> two_tuple
(1, 5)
```

- There is a little complication when making a tuple with one element:

```python
>>>
>>> not_a_tuple = (1)
>>> not_a_tuple
1
```

- This is because Python can’t tell that you meant this to be a tuple, rather than an expression with parentheses round it:

```python
>>>
>>> not_a_tuple = (1 + 5 + 3)
>>> not_a_tuple
9
```

- To tell Python that you mean this to be a length-one tuple, add a comma after the element, and before the closing parenthesis:

```python
>>>
>>> one_tuple = (1,)
>>> one_tuple
(1,)

```


## Dictionary

- It is similar to a list, except that you access its values by looking up a key instead of an index. A key can be any string or a number. Dictionaries are enclosed in curly braces e.g. dct = {'key1' : "value1", 'key2' : "value2"}

```py
phone_book = {"John": 123, "Jane": 234, "Jerard": 345} # "John", "Jane" and "Jerard" are keys and numbers are values
print(phone_book)

# Add new item to the dictionary
phone_book["Jill"] = 345
print(phone_book)

# Remove key-value pair from phone_book
del phone_book['John']

print(phone_book['Jane'])

```

- There are a lot of useful methods in dictionaries such as `keys()` and `values()`. You can explore the rest using Ctrl + Space after a dict_name followed by a dot.

```py
phone_book = {"John": 123, "Jane": 234, "Jerard": 345}  # create new dictionary
print(phone_book)

# Add new item to the dictionary
phone_book["Jill"] = 456
print(phone_book)

print(phone_book.keys())

print(phone_book.values())

// in 
grocery_list = ["fish", "tomato", 'apples']   # create new list

print("tomato" in grocery_list)    # check that grocery_list contains "tomato" item

grocery_dict = {"fish": 1, "tomato": 6, 'apples': 3}   # create new dictionary

print("fish" in grocery_list)

```

- More adding in dictionary

```py 
squares = {1: 1, 2: 4, 3: "error", 4: 16,}
squares[8] = 64
squares[3] = 9
print(squares)
```

- use of `in` and `notin`

To determine whether a key is in a dictionary, you can use in and not in, just as you can for a list.

```py
mums = { 1: one,
         2: two, }

print ( 1 in mums) # true
print (4 not in nums) # True

```

- A useful dictionary method is `get`. It does the same thing as indexing, but if the key is not found in the dictionary it returns another specified value instead ('None', by default).

```py
pairs = { 1: apple,
           "orange": [1,2,3],
        True: False,
        None: "True"
}

print(pairs.get("orange")) # [1,2,3]
print(pairs.get(7)) # None
print(pairs.get(123,"not in this dictionary!")) # not in this dictionary!
# Remove key-value pair from phone_book
del phone_book['John']
print(phone_book['Jane'])

```

- There are a lot of useful methods in dictionaries such as keys() and values(). You can explore the rest using Ctrl + Space after a dict_name followed by a dot. 

```py
phone_book = {"John": 123, "Jane": 234, "Jerard": 345}  # create new dictionary
print(phone_book)

# Add new item to the dictionary
phone_book["Jill"] = 456
print(phone_book)

print(phone_book.keys())

print(phone_book.values())

// in 
grocery_list = ["fish", "tomato", 'apples']   # create new list

print("tomato" in grocery_list)    # check that grocery_list contains "tomato" item

grocery_dict = {"fish": 1, "tomato": 6, 'apples': 3}   # create new dictionary

print("fish" in grocery_list)
```

## Iteration

- for loop is used to iterate each item in a list or any other collection, while can also be used for this purpose.

```py
numbers = list[1,2,3,4,5,6,7,8,9,10]
counter = len(numbers)
index = 0
while index <= counter - 1:
    do some operations

```

- The easy alternative for the above is for loop which exist in most of the languages, in some language it is used as foreach.

```py
for (... in list):
    do some operation

words = ["hello2","me", "day2"]
for w in words:
    print(w)

# similarly slice can be used

```


```py
>>>
>>> for i in range(10):
...     print(i)
0
1
2
3
4
5
6
7
8
9
Identation is crucial!

>>>
>>> # for i in range(10):
>>> # print(i)
Watch out for mistakes:

>>>
>>> for i in range(10):
...     j = i + 1
>>> print(j)
10
Ifs and breaks
>>>
>>> a = 2
>>> b = 5
>>> c = a + b
>>> if c < 6:
...     print("yes")
>>>
>>> if c < 6:
...     print("yes")
... else:
...     print("no")
no
>>>
>>> if c < 6:
...     print("yes")
... elif c > 6:
...     print("no")
... else:
...     print("kind of")
no
>>>
>>> if True:
...     print("true, true!")
true, true!
>>>
>>> if False:
...     print("never!")
>>>
>>> for i in range(10):
...     if i == 6:
...         break
...     print(i)
0
1
2
3
4
5
>>>
>>> for i in range(10):
...     if i == 6:
...         continue
...     print(i)
0
1
2
3
4
5
7
8
9
```

- The easy alternative for the above is for loop which exist in most of the languages, in some language it is used as foreach.

```py
for (... in list):
    do some operation
```


## Function

- In python a variabl or a funciton must be defined first before it can be used, it is unlike js, but like other strongly typed languages.

- Same as in any other language except `def` is used instead of `function` or any language specific identifier. similarly `return` keyword is used like js.
- Scoping of variables applies with the block, variable defined in function blocks are local to only that function and are only visible inside the function. 

- def key word is used to declare function
- In python, funciton are objects and can be assinged to any variable and passed like an objects as js.
- If an argument passed is a function, then recieving function must know and treat it as a fucniton.

- You can import a module or object under a different name using the as keyword. This is mainly used when a module or object has a long or confusing name.

```py
#For example:
#from math import sqrt as square_root

print(square_root(100))

```


```python
def hello_world(): # function definition
    print("It is a string!")

// invoking a function
hello_world()

// passing a parameter
def foo(x):
    print("x is =" + x)

foo(10)

// To return a variable just use return value

// passing a function as a parameter

def multiply(x,y):
    return x*y

# define another function
def repeat(func,x,y)
    return func(func(x,y),func(x,y))

a =2
b =8

// call multiply
print (repeat(multiply,a,b))

# return a variable just use return value
```

## Classes and Objects in Python

- Declaring a class

```python
class MyClass:
    x = 10;
    def grow(num):
        print(num + num)

// Declaring an object of class
maths_class = MyClass()
mathis_class.grow(10) // calling an object

```

- `self` in Python is equal to `this`in js and pointer * in c to give a reference to its method to access the variable inside the function.The self parameter is a Python convention. self is the first parameter passed to any class method. Python will use the self parameter to refer to the object being created. 

```py

```

- A constructor method in Python is `__init__(self)`


### Modules and packages

- Modules in Python are simply Python files with the .py extension containing Python definitions and statements. Modules can be handy when you want to use your function in a number of programs without copying its definition into each program. Modules are imported from other modules using the import keyword and the file name without an extension. The first time a module is loaded into a running Python script, it is initialized by executing the code in the module once. 

- A module is written in a following way and saved in a file say my_module.py then this file is imported in another file,when it is imported it is run once.

```py
""" documentation string for module my_module
This module contains hello_world function
"""
def hello_world(name):
    print("Hello, World! My name is %s" % name)
```

- The idea is same, you define some function in one file, and import the whole module in an other file and use its functionality. If only one method is needed to be imported it can be done by using `from ..... import .....` where first ... are filled with the module name and the second one is filled with method name.

### Built in Module

- Python comes with a library of standard modules. Remember that you can use Ctrl + Space after a dot (.) to explore available methods of a module. 

### Read and Write file

- To read file use ` file = open("filename","r")` in read mode. Then read its text using `for lines in f.readlines():` and then get it printed using print(lines) and then close th stream ` file.close()`

```py

f = open("input.txt", "r")   # here we open file "input.txt". Second argument used to identify that we want to read file
                             # Note: if you want to write to the file use "w" as second argument

for line in f.readlines():   # read lines
    print(line)

f.close()                   # It's important to close the file to free up any system resources.

f1 = open("input1.txt", "r")

for i in f1.readlines():
    print(i)
    break  // To break after first line

f1.close()
```

- If you open a file using "w" (write) as the second argument, a new empty file will be created. Note that if another file with the same name exists, it will be deleted. If you want to add some content to an existing file, you should use the "a" (append) modifier. 

```py
zoo = ['lion', "elephant", 'monkey']

if __name__ == "__main__":
    f = open("output.txt", "a")

    for i in zoo:
        f.write(i)
        f.write(" ")

    f.close()

```

### Files:Write lines to a text file:

```py
>>>
>>> fobj = open("/tmp/important_notes.txt", "wt")
>>> type(fobj)
<...>
>>>
>>> fobj.write("captains log 672828: I had a banana for breakfast.\n")
51
>>> fobj.write("captains log 672829: I should watch less TV.\n")
45
>>> fobj.close()
Read lines from a text file:

>>>
>>> fobj = open("/tmp/important_notes.txt", "rt")
>>> print(fobj.readline())
captains log 672828: I had a banana for breakfast.

>>> print(fobj.readline())
captains log 672829: I should watch less TV.
>>>
>>> print(fobj.readline())
Close a file when you’ve finished with it:

fobj.close()
One way to read all the lines from a text file:

>>>
>>> fobj = open("/tmp/important_notes.txt", "rt")
>>> lines = fobj.readlines()
>>> fobj.close()
>>> len(lines)
2
>>> print(lines[0])
captains log 672828: I had a banana for breakfast.
``` 

### Working with files

- A new way to open files is to use:

```py
with open(filename) as f:
    print(f.read())

# or 
try:
    print(1)
    assert 2+2 ==5
except AssertionError:
    print(3)
except:
    print(4)
```


## Range in Python 3 returns a “range object”. It’s like a list, but isn’t quite a list.

- range in Python 3 returns a range object. It is a sequence, and so it is rather like a list [4]. When you use range with one argument, the argument value is the stop index. For example, to make a range object generating the numbers from 0 up to but not including 5:

```
>>>
>>> my_range = range(5)
>>> my_range
range(0, 5)
You can make a range object into a list by using list:

>>>
>>> list(range(5))
[0, 1, 2, 3, 4]
A range object is a sequence:

>>>
>>> # Has a length
>>> len(my_range)
5
>>> # Is iterable
>>> for e in my_range:
...    print(e)
0
1
2
3
4
>>> # Can be indexed
>>> my_range[1]
1
>>> # Can be sliced
>>> my_range[0:2]
range(0, 2)
>>>
>>> range(10)
range(0, 10)
```

- You can make it into a list by using the list constructor. A constructor is like a function, but it creates a new object, in this case a new object of type list.

```
>>>
>>> list(range(10))
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
You can also set the start element for range:
>>>
>>> list(range(2, 7))
[2, 3, 4, 5, 6]
Use in to ask if a element is a collection of things, such as a range, or a list:
>>>
>>> 5 in range(2, 7)
True
>>> 5 in [2, 5, 7]
True
>>>
>>> 9 in range(2, 7)
    False
    Sets
    Sets are unordered, and unique.
```

> “Unordered” means the order is arbitrary, and Python reserves the right to return the elements in any order it likes:

```
>>>
>>> our_work = set(["metacognition", "mindwandering", "perception"])
>>> print(our_work)  
{'mindwandering', 'perception', 'metacognition'}
If you want to get a version of the set that is ordered, use sorted, which returns a sorted list:
>>>
>>> sorted(our_work)
['metacognition', 'mindwandering', 'perception']
You can’t index a set, because the indices 0, or 1, or 2 don’t correspond to any particular element (because the set is unordered):
>>>
>>> our_work[0]
Traceback (most recent call last):
...
TypeError: 'set' object does not support indexing
Add to a set with the add method:
>>>
>>> our_work.add("consciousness")
>>> print(our_work)  
{'mindwandering', 'perception', 'metacognition', 'consciousness'}
>>>
>>> our_work.add("consciousness")
>>> print(our_work)  
{'mindwandering', 'perception', 'metacognition', 'consciousness'}
>>> our_work.add("consciousness")
>>> print(our_work)  
{'mindwandering', 'perception', 'metacognition', 'consciousness'}
You can subtract sets:
>>>
>>> competing_labs_work = set(["motor control", "decision making", "memory", "consciousness"])
>>> what_we_should_focus_on = our_work - competing_labs_work
>>> print(what_we_should_focus_on)  
{'mindwandering', 'perception', 'metacognition'}
>>>
>>> what_we_should_avoid = our_work.intersection(competing_labs_work)
>>> print(what_we_should_avoid)
{'consciousness'}
Sets have lengths as well:
>>>
>>> len(what_we_should_focus_on)
3
```

### Set the start element for range by passing two arguments:

```
>>>
>>> my_range = range(1, 7)
>>> my_range
range(1, 7)
>>> list(my_range)
[1, 2, 3, 4, 5, 6]
Set the step size with a third argument:
>>>
>>> my_range = range(1, 7, 2)
>>> my_range
range(1, 7, 2)
>>> list(my_range)
[1, 3, 5]
One common use of range is to iterate over a sequence of numbers in a for loop:
>>>
>>> for i in range(5):
...    print(i)
...
0
1
2
3
4
Sets
Sets are collections of unique elements, with no defined order. Python reserves the right to order set elements in any way it chooses:
>>>
>>> # Only unique elements collected in the set
>>> my_set = set((5, 3, 1, 3))
>>> my_set  
{1, 5, 3}
Because there is no defined order, you cannot index into a set:
```



## Reusing code

- DRY principle : Dont repeat yourself
- WET principle : We enjoy typing

### Function Calls

```py

print("Hello world!")
range(2, 20)
str(12)
range(10, 20, 3)

```


### Docstrings

- (documentation strings) serve a similar purpose to comments, as they are designed to explain code. However, they are more specific and have a different syntax. They are created by putting a multiline string containing an explanation of the function below the function's first line.

```
 """
  Print a word with an
  exclamation mark following it.
  """
```

## Standard library or built-in module

- Python standard  library like other languages is installed when Python is installed which contains many useful functions such as string, re, datetime, math, random os, multiprocessing, subproces,socket , email, json, doctest, unittest, pdf, argpares and sys.
- It is a very extensive standard library.
- Some of the modules in the standard library are written in Python, and some are written in C. Most are available on all platforms, but some are Windows or Unix specific.ly too many. The complete documentation for the standard library is available online at www.python.org
- Many third-party Python modules are stored on the Python Package Index (PyPI).
- The best way to install these is using a program called pip. 
- This comes installed by default with modern distributions of Python. If you don't have it, it is easy to install online. Once you have it, installing libraries from PyPI is easy. 
- Look up the name of the library you want to install, go to the command line (for Windows it will be the Command Prompt), and enter pip install library_name. Once you've done this, import the library and use it in your code.
- Using pip is the standard way of installing libraries on most operating systems, but some libraries have prebuilt binaries for Windows. These are normal executable files that let you install libraries with a GUI the same way you would install other programs.

## `None` object is used to represent the absence of a value.

- It is similar to null in other programming languages. Like other "empty" values, such as 0, [] and the empty string, It is False when converted to a Boolean variable. When entered at the Python console, it is displayed as the empty string.
 
- The None object is returned by any function that doesn't explicitly return anything else.

- None is also a special object in Python. By convention, Python often uses None to mean that no valid value resulted from an operation, or to signal that we don’t have a value for a parameter.

```py

>>>
>>> type(None)
<class 'NoneType'>
Unlike most other values in Python, the default display output from None, is nothing:

>>>
>>> None
Equals
As for MATLAB and R, = is for assignment, == is for testing equality.

>>>
>>> a = 1
>>> a
1
>>> a == 1
```


- ## Common Python Exceptions

    - importError: an import fails;
    - IndexError: a list is indexed with an out-of-range number;
    - NameError: an unknown variable is used;
    - SyntaxError: the code can't be parsed properly;
    - TypeError: a function is called on a value of an inappropriate type;
    - ValueError: a function is called on a value of the correct type, but with an inappropriate value.
- 
- To handle exceptions, and to call code when an exception occurs, you can use a **try/except** statement.
- 
- The try block contains code that might throw an exception. If that exception occurs, the code in the try block stops being executed, and the code in the except block is run. If no error occurs, the code in the except block doesn't run.

- A try statement can have multiple different `except` blocks to handle different exceptions. Multiple exceptions can also be put into a single except block using parentheses, to have the except block handle all of them.
- Try catch finlly is also availale in python, in fact another version is present 
- 
### Raising Exception

- An exception can be raised forcefully by using `raise` command as raise(ValueError)

## Assertion

- Programmers often place assertions at the start of a function to check for valid input, and after a function call to check for valid output.

## Microsoft Curriculum (image from coursera)

![Fundamentals.png](/images/python/Fundamentals.png)


## Numbers

- There are two types of numbers in Python: integer and floating point. In Python, an integer is an object of type int, and a float is an object of type float.

```py
    >>>
    >>> a = 99
    >>> type(a)
    <class 'int'>
    >>> b = 99.0
    >>> type(b)
    <class 'float'>
```

- You can create ints and floats by using int and float like this:

```py
>>>
>>> float('1')
1.0
>>> float(1)
1.0
>>> int('1')
1
>>> int(1)
1
+, -, * or / on a mix of floats and ints, give floats:
>>>
>>> a + b
198.0
>>> a * b
9801.0
```

- Dividing an int by an int also gives a float – but this is only true by default for Python >= 3 (see [1]):

```>>>
>>> 1 / 2
0.5
If you only want the integer part of the division, use //
>>>
>>> 1 // 2
0
>>> 1.0 // 2.0
0.0
```

- Python has built-in function called round:

```
>>>
>>> round(5.0 / 2.0)
2
The % operator on numbers gives you the remainder of integer division (also known as the modulus):

>>>
>>> 5 % 2
1
>>>
>>> 5.0 % 2.0
1.0
```
---

[//]: #( check the contents below and correct it)

```py
>>> print ('C:This is my \name') # C:This is my 
name # a new line is printed because of `\n` new line escape character, but if you put `r` a raw string it is avoided
>>>print(r'C:This is my \name') 

```

- String literal ( a literal means something that is enclosed in quotes) can be span multiple lines. One way is tuse triple quotes `'''......'''` or `"....."
```py
print("""\
This is a new line:
so is This

the abo ve is a blank line and now some tabs            after tabs some :::no-loc text="":::
""") # end
```
- Note: String literals next to each other are automatically concatenated. "hell" "o" will become hello. It is useful when a long string can be broken into two lines.
- But a variable and literal can not be concatenated without a + sign.


```py
x = `hello`
y = x `python` # error you need to use `+`
y = x + `python` # is right.

```

- With string `indexing ` and `slicing` is allowed like done with lists or arrays.

```py
>>> word[:2]   # character from the beginning to position 2 (excluded)
'Py'
>>> word[4:]   # characters from position 4 (included) to the end
'on'
>>> word[-2:]  # characters from the second-last (included) to the end
'on'



+---+---+---+---+---+---+
 | P | y | t | h | o | n |
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6
-6  -5  -4  -3  -2  -1
```


