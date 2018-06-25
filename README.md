# Automate-the-Boring-Stuff
Code solutions for the Book Automate the Boring stuff by AL Sweigart

## Chapter 1: Python Basics
### What Is Python?
Python refers to the Python programming language (with syntax rules for writing what is considered valid Python code) and the Python interpreter software that reads source code (written in the Python language) and performs a given set of instructions.
Expressions consist of values and operators (such as +), and they can always evaluate (reduce) down to a single value.
 
### String concatenation & Replication
   
### Assignment Statements
You’ll store values in variables with an assignment statement. An assignment statement consists of a variable name, an equal sign (called the assignment operator), and the value to be stored.
Valid & Invalid variable names
 
A variable is initialized (or created) the first time a value is stored in it. After that, you can use it in expressions with other variables and values.When a variable is assigned a new value w, the old value is forgotten, which is why spam evaluated to 42 instead of 40 at the end of the example. This is called overwriting the variable.
 
### Your first Python Program:

# This program says hello and asks for my name.

```python
print('Hello world!')
print('What is your name?')    # ask for their name
myName = input()
print('It is good to meet you, ' + myName)
print('The length of your name is:')
print(len(myName))
print('What is your age?')    # ask for their age
myAge = input()
print('You will be ' + str(int(myAge) + 1) + ' in a year.')
```

### Comments

#### Single Line Comment
‘’’

#### Multi Line Comments
‘’’
 
### Typecasting and different datatypes
Int(), Str(), Float()
```python
>>> str(0)
'0'
>>> str(-3.14)
'-3.14'
>>> int('42')
42
>>> int('-99')
-99
>>> int(1.25)
1
>>> int(1.99)
1
>>> float('3.14')
3.14
>>> float(10)
10.0
```
## Chapter 2: Flow Control

Flow control statements can decide which Python instructions to execute under which conditions.
 
In a flowchart, there is usually more than one way to go from the start to the end. The same is true for lines of code in a computer program. Flow-charts represent these branching points with diamonds, while the other steps are represented with rectangles. The starting and ending steps are represented with rounded rectangles.

### Boolean Values: Return a True or False
Assigning True or False to a variable makes it a Boolean variable. 
Comparison Operators
 
These operators evaluate to True or False depending on the values you give them.
```python
>>> 42 == 42
True
>>> 42 == 99
False
>>> 2 != 3
True
>>> 2 != 2
False
```
Note the difference between == and =, one makes a comparison to checks if one number is equal to the other. Whereas the other assigns a value to a variable. 

Binary Boolean Operators make use of ‘and’, ‘or’ and ‘not’

Examples: And: only evaluates to true if both comparison values are the same
```python
>> True and False
False
>> True and True
True
>> False and False
False
>> False and True
False
```

## Examples: 

### Or: only evaluates to true for either or both
```python
>> False or True
True
>> False or False
False
>> True or True
True
>> True or False
True
>> False or True
True
>> False or False
False
```
### Not Operator: Negates the following variable (note the outcome is Boolean)
```python
>> not True
False
>> not not not not True
True
```

### Mixing comparison operators with boolean
```python
>> (4 < 5) and (5 < 6)
True
>> (1 == 2 ) or (2 == 2)
True 
```
### If/Else/Elif statements:
```python
if name == 'Alice':
    print('Hi, Alice.')
elif age < 12:
    print('You are not Alice, kiddo.')
else:
    print(“You’re not Alice nor a kid”)
```

### While statements:
```python
spam = 0
if spam < 5:
    print('Hello, world.')
    spam = spam + 1

spam = 0
while spam < 5:
    print('Hello, world.')
    spam = spam + 1

Break statements: Exit a loop
while True:
    print('Please type your name.')
     name = input()
     if name == 'your name':
         break
 print('Thank you!')
```

### Using Booleans to evaluate a Loop:
```python
# Boolean values in Loops

name = ''
while not name:
    print('Enter your name:')
    name = input()
    # if a blank string is entered, the loop repeats itself
    # Asking the user for a name
    # Only when a non-blank name is entered will we exit the loop
    
print('How many guests will you have ' + name + '?')
numOfGuests = int(input())

if numOfGuests: # i.e. if numOfGuests is a non blank input, else exits
    print(str(numOfGuests) + '! Be sure to have enough room for all your guests.')
print('Done')
For Loops using the range function:
for i in range(5):
	print("Index is = " + str(i))
```
```python
Index is = 0
Index is = 1
Index is = 2
Index is = 3
Index is = 4
```
Note the index I starts at 0 and goes up to range-1.

### Karl Frederich Gauss Example:

Was asked to add up all numbers up to 100. He broke them down into pairs, finding 50 pairs that sum to 100 and one pair summing to 50. 
These were, SUM(1:100) = 99 + 1, 98 + 2, 97 + 3, …., 51 + 49, 50. I.e. 50 pairs add up to 100 then +50 = 5,050. 
With Python 3, this looks like:

```python
 total = 0
 for num in range(101):
     total = total + num
 print(total)  
Tips with the range function
Selecting a slice of an index
Range(5,15)
Counts from 5 to 14..
Using a step argument with range:

for i in range(0, 10, 2):
    print(i)
0
2
4
6
8
Counts to 10 in steps of 2, starting from 0. 
We can use negative numbers as well: 
for i in range(5, -1, -1):
    print(i)
5
4
3
2
1
0
```
### Importing Modules:

Each module is a Python program that contains a related group of functions that can be embedded in your programs. For example, the math module has mathematics related functions, the random module has random number related functions, and so on.

## The Random Function
```python
import random
for i in range(5):
    print(random.randint(1,10)) 
‘’’
randint belongs to Random module, called using the dot function.
Rnadint requires a start and finish number to determine the range
‘’’
# Importing multiple modules on a single line
import random, sys, os, math	
from import Statements
```
An alternative form of the import statement is composed of the from keyword, followed by the module name, the import keyword, and a star; for example, from random import *.
With this form of import statement, calls to functions in random will not need the random. prefix. However, using the full name makes for more readable code, so it is better to use the normal form of the import statement.
ending a Program early with sys.exit()

However, you can cause the program to terminate, or exit, by calling the sys.exit() function. Since this function is in the sys module, you have to import sys before your program can use it.

By using expressions that evaluate to True or False (also called conditions), you can write programs that make decisions on what code to execute and what code to skip. You can also execute code over and over again in a loop while a certain condition evaluates to True. The break and continue statements are useful if you need to exit a loop or jump back to the start. These flow control statements will let you write much more intelligent programs. There’s another type of flow control that you can achieve by writing your own functions, which is the topic of the next chapter.


## Chapter 3: Functions
You’re already familiar with the print(), input(), and len() functions from the previous chapters. Python provides several built-in functions like these, but you can also write your own functions. A function is like a mini- program within a program.
A major purpose of functions is to group code that gets executed multiple times. Without a function defined, you would have to copy and paste this code each time. The benefits are when making changes, only a single change needs to be made within a function that’s used many times. 
A simple example with Functions:
```python
def hello():
    print('Howdy!')
    print('Howdy!!!')
    print('Hello there.')
hello()
```

The first line is a def statement u, which defines a function named hello(). The code in the block that follows the def statement v is the body of the function. This code is executed when the function is called, not when the function is first defined.
Functions require a definition that when called will perform a certain action. It can further take in arguments to be passed by value (the value is only passed on, not the actual variable) and then pass values back. 
```python
def hello(name):
    print('Hello ' + name)
hello('Alice')
hello('Bob')
```
Refer to the magic 8 ball program. Here we have multiple if else statements to signify flow control based on a random number to assign an outcome. 

The None value datatype: 
Represents the absence of a value. In other programming languages this is named null, nil or undefined. This is similar to a Boolean value and must start with a capital letter. 

When printed – the value None is displayed to the screen.

This value-without-a-value can be helpful when you need to store something that won’t be confused for a real value in a variable. One place where None is used is as the return value of print(). The print() function displays text on the screen, but it doesn’t need to return anything in the same way len() or input() does.

NB: None is the return value of a function that doesn’t return anything. It’s also a good storage value for variables that will be assigned real values like integers or characters. 

Multi-line arguments with the print function

### Multiline arguments and print()
print('Hello', end= ' ')
print('World')
is the same as: 
print('Hello', end = ' '), print('World')
or we could even do;
>>> print('cats', 'dogs', 'mice')
cats dogs mice
we can use the separate function to add a separator between what we print.
>>> print('cats', 'dogs', 'mice', sep = ', ')
cats, dogs, mice

### Local and Global Variables
Parameters and variables that are assigned in a called function are said to exist in that function’s local scope. Variables that are assigned outside all functions are said to exist in the global scope.
After a function is called and a value it’s purpose completed, the local variable is destroyed. It cannot be accessed outside the function, unless returned back.
To typecast a local variable to a global variable use the global statement.
def spam():
    global eggs
    eggs = 'spam'
eggs = 'global'
spam()
print(eggs) 
>> Spam
Error handling

We don’t want the program to crash whenever we encounter an error. Rather we want to detect errors, handle their outcome and allow the program to continue running. 
Error handling can be done with if, else statements but Python has a unique error handling set of syntax called try and except. In order to use the except keyword, we need the exact name of the error. Before attempting the code below, divide a number by 0 in the interpreter and see what the error name is. 
def spam(divideBy):
    try:
        return 42 / divideBy
    except ZeroDivisionError:
        print(‘Error: Cannot divide by zero’)
>> print(spam(2))
>> print(spam(12))
>> print(spam(0))
>> print(spam(1))

21.0
3.5
Error: Invalid argument.
None
42.0
When code in a try clause causes an error, the program execution immediately moves to the code in the except clause. After running that code, the execution continues as normal. The output of the previous program is as follows:


Chapter 4: Lists
Lists and tuples can contain multiple values, which makes it easier to write programs that handle large amounts of data. And since lists themselves can contain other lists, you can use them to arrange data into hierarchical structures.
 
List definition and access:
>>> spam = ['cat', 'bat', 'rat', 'elephant']
>>> spam[0]
'cat'
>>> spam[1]
'bat'
>>> spam[2]
'rat'
>>> spam[3]
'elephant'
>>> ['cat', 'bat', 'rat', 'elephant'][3]
'elephant'
u >>> 'Hello ' + spam[0]
v 'Hello cat'
>>> 'The ' + spam[1] + ' sat on the ' + spam[0] + '.'
'The bat sat on the cat.'

Lists can also contain other list values. The values in these lists of lists can be accessed using multiple indexes, like so:
>>> spam = [['cat', 'bat'], [10, 20, 30, 40, 50]]
>>> spam[0]
['cat', 'bat']
>>> spam[0][1]
'bat'
>>> spam[1][4]
50
### Negative Indexes
While indexes start at 0 and go up, you can also use negative integers for the index. The integer value -1 refers to the last index in a list, the value -2 refers to the second-to-last index in a list, and so on. Enter the following into the interactive shell:
```python
>>> spam = ['cat', 'bat', 'rat', 'elephant']
>>> spam[-1]
'elephant'
>>> spam[-3]
'bat'
>>> 'The ' + spam[-1] + ' is afraid of the ' + spam[-3] + '.'
```
```
'The elephant is afraid of the bat.'	
```
### Slices from a list, using the colon:
As a shortcut, you can leave out one or both of the indexes on either side of the colon in the slice. Leaving out the first index is the same as using 0, or the beginning of the list. Leaving out the second index is the same as using the length of the list, which will slice to the end of the list. Enter the following into the interactive shell:
```python
>>> spam = ['cat', 'bat', 'rat', 'elephant']
>>> spam[0:4]
['cat', 'bat', 'rat', 'elephant']
>>> spam[1:3]
['bat', 'rat']
>>> spam[0:-1]
['cat', 'bat', 'rat']
```
The first index dictates which list to use, and the second indicates ghe value within the list value. For example, spam[0][1] prints 'bat', the second value in the first list. If you only use one index, the program will print the full list value at that index.
Note we can access values from the back using negative indices. 
We count the number of values in a list using len. Note if we have a list that includes multiple sub lists, it will return the number of sub-lists it contains. 
```python
Spam = [[‘cat’, ’rat’, ‘bat’] , [10,20,30,40,50]]
Len(spam) = 2
Len(spam[0]) = 3
Lem(spam[1]) = 5
```
### Changing Values in a List with Indexes:
```python
>>> spam[0][0] = 'aardvark'
>>> spam
[['aardvark', 'bat', 'rat'], [10, 20, 30, 40, 50]]
```
### List Concatenation and List Replication
The + operator can combine two lists to create a new list value in the same way it combines two strings into a new string value. The * operator can also be used with a list and an integer value to replicate the list. Enter the following into the interactive shell:
```python
>>> [1, 2, 3] + ['A', 'B', 'C']
[1, 2, 3, 'A', 'B', 'C']
>>> ['X', 'Y', 'Z'] * 3
['X', 'Y', 'Z', 'X', 'Y', 'Z', 'X', 'Y', 'Z']
>>> spam = [1, 2, 3]
>>> spam = spam + ['A', 'B', 'C']
>>> spam
[1, 2, 3, 'A', 'B', 'C']
```
### Cat Names example:
```python
# Cat names
# Have the user enter several cat names, store it into a list and print them.
catNames = [] # Empty List
while True:
    print('Enter the name of cat ' + str(len(catNames) + 1) + 
      ' (Or enter nothing to stop.):')
    name = input()
    if name == '': # If empty string entered, break while loop
        break
    catNames = catNames + [name]  # list concatenation can only concatenate the same data type
print('The cat names are:')
for name in catNames:
    print('  ' + name)
For loops and lists
The following are the same
for i in range(4):
    print(i)
and
for i in [0, 1, 2, 3]:  # This data type is called a sequence
    print(i)
```
Gives the following output: 
```
0
1
2
3
```
When we don’t know how long a list will be, we can use len(range(list)) like the following:
```python
>>> supplies = ['pens', 'staplers', 'flame-throwers', 'binders']
>>> for i in range(len(supplies)):
    print('Index ' + str(i) + ' in supplies is: ' + supplies[i])
```
```
Index 0 in supplies is: pens
Index 1 in supplies is: staplers
Index 2 in supplies is: flame-throwers
Index 3 in supplies is: binders
```
### The in and not in Operators
You can determine whether a value is or isn’t in a list with the in and not in operators. These expressions will evaluate to a Boolean value. 

Example:
```python
>>> foo = ['hi','hello','howdy','heya']
>>> 'howdy' in foo
True
>>> 'konichiwa' in foo
False
Pet names:
myPets = ['Zophie', 'Pooka', 'Fat-tail']
print('Enter a pet name:')
name = input()
if name not in myPets:
    print('I do not have a pet named ' + name)
else:
    print('Yes ' + name + ' is my pet.')
```

### The Multiple Assignment Trick
The multiple assignment trick is a shortcut that lets you assign multiple variables with the values in a list in one line of code. The following is the same:
```python
>>> cat = ['fat', 'black', 'loud']
>>> size = cat[0]
>>> color = cat[1]
>>> disposition = cat[2]
Is the same as:
>>> cat = ['fat', 'black', 'loud']
>>> size, color, disposition = cat
```
The number of variables and the length of the list must be exactly equal, or a ValueError occurs:
Augmented Assignment operators: 

This is just like C. 
Value = Value + 1: +=1
Value = Value - 1:   -= 1
Value = Value * 1:   *=1
Value = Value / 1:  /= 1
Value = Value % 1: %= 1
These operators can be used for string concatenation and replication. 
```python
>> Spam = ‘Hello’
>> Spam =+ ‘ World’
>> Spam 
‘Hello World’
```
### String repetition 
Bacon = [‘Zophie’]
Bacon *= 3
Bacon 
[‘Zophie’,’Zophie’,’Zophie’]

### Methods:
A method is the same thing as a function, except it is “called on” a value, using the ‘.’ dot notation. 
Each data type has it’s own set of methods().

For example: spam.index(‘Hello’) will return the index value where ‘hello’ is stored within spam. If the value doesn’t exist, a ValueError will be passed back. If duplicates are found in the list, then the first instance of the value index will be returned. Same goes for remove, the first instance of the value will be removed. 
List methods using append(), insert() and remove() methods.

The previous append() method call adds the argument to the end of the list.
```python
>>> spam = ['cat', 'dog', 'bat']
>>> spam.append('moose')
>>> spam
['cat', 'dog', 'bat', 'moose']
```
The insert() method can insert a value at any index in the list. The first argument to insert() is the index for the new value, and the second argument is the new value to be inserted. Note methods don’t have a return value.
```python
>>> spam = ['cat', 'dog', 'bat']
>>> spam.insert(1, 'chicken')
>>> spam
['cat', 'chicken', 'dog', 'bat']
```
### Remove:
```python
>>> spam = ['cat', 'bat', 'rat', 'elephant']
>>> spam.remove('bat')
>>> spam
['cat', 'rat', 'elephant']
```
•	Removing a value that doesn’t exists returns a ValueError.
•	These methods are only applicable to lists. They are modified in place and don’t need assignment or return values. 
•	If we tried them on strings or integers we would receive an attribute error. 
•	When you know the index, use del(). If you only know the value, use remove()
•	Sort a list using .sort()

### Sort() in action:
```python
numList = [11,4,3.3417,15,-7,-21,0,42,3,9,5,7,4,2,3,6]
>>> numList.sort()
>>> numList
[-21, -7, 0, 2, 3, 3, 3.3417, 4, 4, 5, 6, 7, 9, 11, 15, 42]
>>> animalList=['antelope','anteater','aardvark','armadillo','anaconda','albatross', 'alligator']
>>> animalList.sort()
>>> animalList
['aardvark', 'albatross', 'alligator', 'anaconda', 'anteater', 'antelope', 'armadillo']
```
Note – Items in capitals will supersede lowercase letters
Sort in reverse: 
```python
>>> spam.sort(reverse=True)
>>> spam
['elephants', 'dogs', 'cats', 'badgers', 'ants']
Creating unique list items: Sets
>>> t = [1, 2, 3, 1, 2, 5, 6, 7, 8]
>>> t
[1, 2, 3, 1, 2, 5, 6, 7, 8]
>>> list(set(t))
[1, 2, 3, 5, 6, 7, 8]
>>> s = [1, 2, 3]
>>> list(set(t) - set(s))
[8, 5, 6, 7]
```
### Examples:
```python
>>> sample = ['bat','cat','antelope','aardvark','cougar','puma','racoon']
>>> sample.append('moose')
>>> sample
['bat', 'cat', 'antelope', 'aardvark', 'cougar', 'puma', 'racoon', 'moose']
>>> sample.index('cat')
1
>>> sample.index('bat')
0
>>> sample.insert(1,'chicken')
>>> sample
['bat', 'chicken', 'cat', 'antelope', 'aardvark', 'cougar', 'puma', 'racoon', 'moose']
>>> sample.sort()
>>> sample
['aardvark', 'antelope', 'bat', 'cat', 'chicken', 'cougar', 'moose', 'puma', 'racoon']
>>> sample.sort(reverse = True)
>>> sample
['racoon', 'puma', 'moose', 'cougar', 'chicken', 'cat', 'bat', 'antelope', 'aardvark']
```
Notes about sort:
•	Sort cannot differentiate between numbers and letters
•	Sort ‘sorts’ numbers in ASCIIbetical order so capitals come before short hand. 

Indentation, makes lists look nicer, how to extend on multiple lines
You can also split up a single instruction across multiple lines using the \ line continuation character at the end . Think of \ as saying, “This instruction continues on the next line .” The indentation on the line after a \ line continuation is not significant . For example, the following is valid Python code:
```python
print('Four score and seven ' + \
      'years ago...')
```
```python
# Magic 8 Ball with Lists

import random

messages =[
    'It is certain',
    'It is decidedly so',
    'Yes definitly',
    'Reply hazy try again',
    'Ask again later',
    'Concentrate and ask again',
    'My reply is no',
    'Outlook not so good',
    'Very Doubtful']
print(messages[random.randint(0, len(messages)-1)])
```
### Low level string manipulation
```python
>>> name = 'Zophie'
>>> name[0]
'Z'
>>> name[-2]
'i'
>>> name[0:4]
'Zoph'
>>> 'Zo' in name
True
>>> 'z' in name
False
>>> 'p' not in name
False
>>> for i in name:
        print('* * * ' + i + ' * * *')
```
### Mutable and Immutable Data Types
But lists and strings are different in an important way. A list value is a mutable data type: It can have values added, removed, or changed. However, a string is immutable: It cannot be changed. Trying to reassign a single character in a string results in a TypeError error.
The proper way to “mutate” a string is to use slicing and concatenation to build a new string by copying from parts of the old string. Enter the following into the interactive shell:
```python
>>> name = 'Zophie a cat'
>>> newName = name[0:7] + 'the' + name[8:12]
>>> name
'Zophie a cat'
>>> newName
'Zophie the cat'
```
### The Tuple Data Type
The tuple data type is almost identical to the list data type, except in two ways. First, tuples are typed with parentheses, ( and ), instead of square brackets, [ and ]. For example, enter the following into the interactive shell:
```python
>>> eggs = ('hello', 42, 0.5)
>>> eggs[0]
'hello'
>>> eggs[1:3]
(42, 0.5)
>>> len(eggs)
3
```
But the main way that tuples are different from lists is that tuples, like strings, are immutable. Tuples cannot have their values modified, appended, or removed. 
If you have only one value in your tuple, you can indicate this by placing a trailing comma after the value inside the parentheses. Otherwise, Python will think you’ve just typed a value inside regular parentheses.
You can use tuples to convey to anyone reading your code that you don’t intend for that sequence of values to change. If you need an ordered sequence of values that never changes, use a tuple. A second benefit of using tuples instead of lists is that, because they are immutable and their contents don’t change, Python can implement some optimizations that make code using tuples slightly faster than code using lists.
```python
>>> type(('hello',))
<class 'tuple'>
>>> type(('hello'))
<class 'str'>
Converting a tuple to a list is handy if you need a mutable version of a tuple value.
>>> type(eggs)
<class 'tuple'>
>>> eggslist = list(eggs)
>>> type(eggslist)
<class 'list'>
>>> list('Hello')
['H', 'e', 'l', 'l', 'o']
Pass by value and pass by reference
When we reassign values to a variable, the variable stores the latest value. However what happens with lists?
>>> spam = [0, 1, 2, 3, 4, 5]
>>> cheese = spam
>>> cheese[1] = 'Hello!'
>>> spam
[0, 'Hello!', 2, 3, 4, 5]
>>> cheese
[0, 'Hello!', 2, 3, 4, 5]
```
Looking at the above, we see both variables Spam and Cheese have been changed. Why did this happen? When we reassign variables to lists, we actually pass a reference to the original list. Therefore any changes we apply to the variable – will refer to that one list and make relative changes. 

When you create the list u, you assign a reference to it in the spam variable. But the next line v copies only the list reference in spam to cheese, not the list value itself. This means the values stored in spam and cheese now both refer to the same list. There is only one underlying list because the list itself was never actually copied. So when you modify the first element of cheese, you are modifying the same list that spam refers to.

## chapter 5: Dictionaries and Structuring data

Dictionaries stores an array of data pairs. Unlike lists they are unordered. It has the format of:
```python
Dictname = {keys : values, …}
```

Access relevant items in a dictionary using methods such as dictnames.keys() dictname.values(), dictname.items(). 
```python
>>> spam = {'color': 'red', 'age': 42}
>>> for v in spam.values():
        print(v)
red
42
>>> for k in spam.keys():
        print(k)
color
age
>>> for i in spam.items():
        print(i)
('color', 'red')
('age', 42)
>>> spam = {'color': 'red', 'age': 42}
>>> for k, v in spam.items():
        print('Key: ' + k + ' Value: ' + str(v))
Key: age Value: 42
Key: color Value: red
```
## chapter 6: String Manipulation

