# Intermediate Python Programming <!-- omit in toc -->




## Here's a summary of some of the intermediate-level topics for Python programming covered in this [YouTube]((https://www.youtube.com/watch?v=HGOBQPFzWKo&t=213s)) video. <!-- omit in toc -->
<br/>

1. Data types: lists, tuples, dictionaries, sets, and strings
2. Collections: specialized data structures like named tuples, deque, counter, and defaultdict
3. Itertools: functions that work with iterable data types to create efficient iterators
4. Lambda functions: anonymous functions that can take any number of arguments and return a single value
5. Exceptions and Errors: how to handle unexpected events or errors that occur during program execution
6. Logging: techniques for logging program output and error messages
7. JSON: working with JSON data using the built-in json module
8. Random numbers: generating random numbers for various use cases
9. Decorators: modifying or enhancing the functionality of existing functions using decorators
10. Generators: creating iterable sequences using generator functions
11. Threading vs Multiprocessing: understanding the difference between these two techniques for running multiple tasks simultaneously
12. Multithreading: using threads to execute multiple tasks concurrently within a single program
13. Multiprocessing: running multiple processes in parallel to increase program performance
14. Function Arguments: how to pass arguments to functions and work with default arguments, keyword arguments, and variable-length argument lists
15. Shallow vs Deep Copying: understanding the difference between these two techniques for copying objects in Python
16. Context Managers: using the "with" statement to manage resources and ensure proper clean-up of objects after use.
<br/>
<br/>

<!-- omit in toc -->
## Content: 



- [1. Lists](#1-lists)
- [2. Tuples](#2-tuples)
- [3. Dictionaries](#3-dictionaries)
- [4. Sets](#4-sets)
- [5. Strings](#5-strings)
- [6. Collections](#6-collections)
- [7. Itertools](#7-itertools)
- [8. Lambda Functions](#8-lambda-functions)
- [9. Exceptions and Errors](#9-exceptions-and-errors)
- [10. Logging](#10-logging)


## Cheat Sheets <!-- omit in toc -->
Python cheat sheets are a useful reference tool for programmers looking to improve their coding skills. They provide a condensed summary of essential syntax and functions, making it easier to write code quickly and accurately. Cheat sheets cover a variety of topics, including data types, control structures, functions, modules, and libraries. Whether you are a beginner or an experienced programmer, Python cheat sheets are a valuable resource to have at your fingertips.
<br/>
<br/>

### [Python Cheat Sheet [pdf 1]](https://courses.cs.washington.edu/courses/cse163/22wi/resources/python-cheat-sheet.pdf) 

### [Python Cheat Sheet [pdf 2]](https://faculty.ncssm.edu/~morrison/resources/python/py_cheat.pdf) 
### [Python Crash Course [Book summary]](https://github.com/ehmatthes/pcc/releases/download/v1.0.0/beginners_python_cheat_sheet_pcc_all.pdf) 
<br/>
<br/>

## 1. Lists
[🔼 Back to top](#content)

```python

```python
# lists: ordered, mutable, allows duplicate elements

mylist = ["banana", "cherry", "apple"]
print(mylist)



item = mylist[0]
print(item) 

for i in mylist:
    print(i) # prints each item in the list



if "banana" in mylist:
    print("yes")
else:
    print("no") # yes if banana is in the list, no if not


print(len(mylist)) # 3; length of list



mylist.append("lemon")
print(mylist) # adds lemon to the end of the list


mylist.insert(1, "blueberry")
print(mylist) # inserts blueberry at index 1



item = mylist.pop()
print(item) # removes last item in list



item = mylist.remove("cherry")
print(mylist) # removes cherry from list


item = mylist.clear()
print(item) # clears the list


mylist.reverse()
print(mylist) # Changes the list; uses in place modification

mylist.sort()
print(mylist) # Changes the list; uses in place modification

mylist = [4, 3, 1, -1, -5, 10]
print(mylist)
new_list = sorted(mylist)
print(new_list) 


mylist = [0] * 5
print(mylist) # [0, 0, 0, 0, 0] duplicates the list 5 times

mylist2 = [1, 2, 3, 4, 5]

new_list = mylist + mylist2
print(new_list) # [0, 0, 0, 0, 0, 1, 2, 3, 4, 5]


#slicing
mylist = [1, 2, 3, 4, 5, 6, 7, 8, 9]
a = mylist[1:5]
print(a) # [2, 3, 4, 5]

#step
b = mylist[::2] # [start:end:step]
print(b) # [1, 3, 5, 7, 9] ; skips every other element


list_org = ["banana", "cherry", "apple"]
list_cpy = list_org # this is not a copy, it is a reference to the original in memory
list_cpy.append("lemon")
print(list_cpy) # ['banana', 'cherry', 'apple', 'lemon']
print(list_org) # ['banana', 'cherry', 'apple', 'lemon']

# to make a copy
list_cpy = list_org.copy()
list_cpy = list(list_org)
list_cpy = list_org[:]

# list comprehension
a = [1, 2, 3, 4, 5, 6]
b = [i*i for i in a] 
print(b) # [1, 4, 9, 16, 25, 36] ; squares each element in a and adds it to b in a new list [expression for item in list]
```
<br/>
<br/>

## 2. Tuples
[🔼 Back to top](#content)
```Python
# Tuple: ordered, immutable, allows duplicate elements

mytuple = ("Max", 28, "Boston")
print(mytuple)

mytuple = tuple(["Max", 28, "Boston"]) # tuple constructor

item = mytuple[0] 
print(item) # Max; prints first item in tuple, same as list

#mytuple[0] = "Tim" # TypeError: 'tuple' object does not support item assignment; tuples are immutable


for i in mytuple:
    print(i) # prints each item in the tuple

if "Max" in mytuple:
    print("yes") # yes if Max is in the tuple, no if not



mytuple = ('a', 'p', 'p', 'l', 'e', 'c')
print(len(mytuple)) # 6; length of tuple

print(mytuple.count('p')) # 2; counts the number of times p appears in the tuple

print(mytuple.index('p')) # 1; returns the index of the first occurrence of p in the tuple

my_list = list(mytuple) # converts tuple to list
print(my_list)

mytuple2 = tuple(my_list) # converts list to tuple
print(mytuple2)


# slicing
a = (1, 2, 3, 4, 5, 6, 7, 8, 9)
b = a[2:5]
print(b) # (3, 4, 5)

b = a[::-1] # reverses the tuple

b = a[1:6:2] # (2, 4, 6) starts at index 1, ends at index 6, steps by 2


# unpacking
mytuple = "Max", 28, "Boston"
name, age, city = mytuple
print(name) # Max
print(age) # 28
print(city) # Boston Elements in the tuple must match the number of variables in the tuple

mytuple = (0, 1, 2, 3, 4)
i1, *i2, i3 = mytuple
print(i1) # 0
print(i2) # [1, 2, 3]
print(i3) # 4 * is called a splat operator; it takes the rest of the elements in the tuple and puts them in a list


# tuples are faster and efficient than lists
import sys
mylist = [0, 1, 2, "hello", True]
mytuple = (0, 1, 2, "hello", True)
print(sys.getsizeof(mylist), "bytes") # 104 bytes
print(sys.getsizeof(mytuple), "bytes") # 88 bytes

import timeit
print(timeit.timeit(stmt="[0, 1, 2, 3, 4, 5]", number=1000000)) # 0.066 seconds
print(timeit.timeit(stmt="(0, 1, 2, 3, 4, 5)", number=1000000)) # 0.011 seconds
```
<br/>
<br/>

## 3. Dictionaries
[🔼 Back to top](#content)
```Python
# Dictionary: key-value pairs, unordered, mutable

my_dict = {"name": "Max", "age": 28, "city": "New York"}
print(my_dict)

my_dict2 = dict(name="Mary", age=27, city="Boston") # dict constructor
print(my_dict2)

value = my_dict["name"]
print(value) # Max; prints value of key name


# dictionaries are mutable; add or change items
my_dict["email"] = "max@mail.com"
print(my_dict) # adds email to dictionary

my_dict["email"] = "madmax@mail.com"
print(my_dict) # overwrites email in dictionary


# delete items
del my_dict["name"]
print(my_dict) # deletes name from dictionary

my_dict.pop("age")
print(my_dict) # deletes age from dictionary

my_dict.popitem()
print(my_dict) # deletes last item from dictionary



my_dict = {"name": "Max", "age": 28, "city": "New York"}
if "name" in my_dict:
    print(my_dict["name"]) # Max;  checks if key name is in dictionary, if not, prints default value


try:
    print(my_dict["lastname"]) # KeyError: 'lastname'; checks if key lastname is in dictionary, if not, prints error
except:
    print("Error")


# loop through dictionary
for key in my_dict:
    print(key) # prints each key in the dictionary

for key in my_dict.keys():
    print(key) # prints each key in the dictionary

for value in my_dict.values():
    print(value) # prints each value in the dictionary

for key, value in my_dict.items():
    print(key, value) # prints each key and value in the dictionary


# copy dictionary
my_dict_cpy = my_dict # copies the reference to the dictionary
print(my_dict_cpy)

my_dict_cpy["email"] = "max@mail.com"
print (my_dict)
print(my_dict_cpy) # adds email to dictionary, and modifies both dictionaries, with assignment operator '=' both dictionaries point to the same reference in memory

my_dict_cpy = my_dict.copy() # actual copies the dictionary
my_dict_cpy = dict(my_dict) # copies the dictionary and creates a new dictionary

# update method
my_dict = {"name": "Max", "age": 28, "email": "max@mail.com"}
my_dict2 = dict(name="Mary", age=27, city="Boston")

my_dict.update(my_dict2) 
print(my_dict) # updates my_dict with my_dict2, overwrites values in my_dict with values in my_dict2, if keys are the same


my_dict = {3: 9, 6: 36, 9: 81}
print(my_dict) # {3: 9, 6: 36, 9: 81}; keys can be numbers

mytuple = (8, 7)
my_dict = {mytuple: 15}
print(my_dict) # {(8, 7): 15}; keys can be tuples
# We can't use lists as keys because lists are mutable and can be changed, it not hashable. Tuples are immutable and can't be changed, so they can be used as keys.
```
<br/>
<br/>

## 4. Sets
[🔼 Back to top](#content)
```Python
# Set: unordered collection of unique elements, mutable (can be changed)

myset = {1, 2, 3, 4, 5, 5, 5} # only unique elements
print(myset) # {1, 2, 3, 4, 5}

myset = set([1, 2, 3, 4, 5, 5, 5]) # set constructor
print(myset) # {1, 2, 3, 4, 5}

myset = set("Hello")
print(myset) # {'e', 'H', 'l', 'o'}; order is not guaranteed

myset = {} # this is a dictionary, not a set
print(type(myset)) # <class 'dict'>


myset = set()
myset.add(1)
myset.add(2)
myset.add(3)

myset.remove(3)

print(myset) # {1, 2}

myset.discard(3) # does not throw an error as remove if 3 is not in the set
myset.clear() # clears the set

myset = {1, 2, 3, 4, 5, 6}
myset.pop() # removes a random element from the set
print(myset) # {2, 3, 4, 5, 6}

for i in myset:
    print(i) # prints each element in the set

if 1 in myset:
    print("yes") # yes if 1 is in the set, no if not
else:
    print("no")


# Union
odds = {1, 3, 5, 7, 9}
evens = {0, 2, 4, 6, 8}
primes = {2, 3, 5, 7}

u = odds.union(evens) # combines the sets
print(u) # {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}



# Intersection
i = odds.intersection(primes) # returns the common elements
print(i) # {3, 5, 7}

i = evens.intersection(odds)
print(i) # {}



# Difference
setA = {1, 2, 3, 4, 5, 6, 7, 8, 9}
setB = {1, 3, 5, 7, 9, 11, 13, 15}

diff = setA.difference(setB) # returns the elements in setA that are not in setB
print(diff) # {8, 2, 4, 6}

diff = setB.difference(setA) # returns the elements in setB that are not in setA
print(diff) # {11, 13, 15}


# Symmetric Difference
diff = setA.symmetric_difference(setB) # returns the elements that are not in both sets
print(diff) # {2, 4, 6, 8, 11, 13, 15}

# Union, intersection, difference will not modify the original sets, they will return a new set



# Update
setA.update(setB) # adds the elements from setB to setA without duplicates
print(setA) # {1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 13, 15}

# intersection_update

setA.intersection_update(setB) # removes the elements from setA that are not in setB
print(setA) # {1, 3, 5, 7, 9}

# difference_update
print(setA) # {1, 3, 5, 7, 9}
print(setB) # {1, 3, 5, 7, 9, 11, 13, 15}
setA.difference_update(setB) # removes the elements from setA that are in setB
print(setA) # set()

# symmetric_difference_update
setA = {1, 2, 3, 4, 5, 6, 7, 8, 9}
setB = {1, 3, 5, 7, 9, 11, 13, 15}
setA.symmetric_difference_update(setB) # removes the elements that are in both sets and adds the elements that are not in both sets
print(setA) # {2, 4, 6, 8, 11, 13, 15}


# subset
setC = {1, 2, 3, 4, 5, 6}
setD = {1, 2, 3}
setE = {7, 8, 9}

print(setC.issubset(setD)) # False; all elements in setC are not in setD


# superset
print(setC.issuperset(setD)) # True; all elements in setD are in setC
print(setD.issuperset(setC)) # False; all elements in setC are not in setD

# disjoint
print(setC.isdisjoint(setD)) # False; there are common elements in both sets
print(setC.isdisjoint(setE)) # True; there are no common elements in both sets

# copy
setF = setC # creates a reference to setC
setF.add(7)
print(setC) # {1, 2, 3, 4, 5, 6, 7}; setC is also modified

setF = setC.copy() # creates a copy of setC
setF = set(setC) # creates a copy of setC


# frozen set
a = frozenset([1, 2, 3, 4]) # immutable set; cannot be changed
print(a) # frozenset({1, 2, 3, 4})
# Union, intersection, difference, symmetric_difference, issubset, issuperset, isdisjoint, copy are supported
```
<br/>
<br/>

## 5. Strings
[🔼 Back to top](#content)
```Python
# Strings: ordered, immutable, text representation

mystring = "Hello World"
print(mystring)


char = mystring[0]
print(char) # H

# mystring[0] = "h" # TypeError: 'str' object does not support item assignment; strings are immutable

# Slicing
substring = mystring[1:5]
print(substring) # ello

substring = mystring[::2] # steps by 2
print(substring) # HloWrd

# Concatenation
greeting = "Hello"
name = "Tom"
sentence = greeting + " " + name
print(sentence) # Hello Tom

# Iterating
for i in greeting:
    print(i) # prints each character in the string

# in operator
if "e" in greeting:
    print("yes") # yes if e is in the string, no if not
else:
    print("no")    



# String formatting
string_2 = "Hello"
string_2 = string_2.strip() # removes whitespace
print(string_2) # Hello; immutable does not change the original string

string_2 = string_2.upper() # converts to uppercase
string_2 = string_2.lower() # converts to lowercase

print(string_2.startswith("he")) # True; checks if string starts with He
string_2.endswith("He") # False; checks if string ends with He

string_2 = string_2.find("l") # 2; returns the index of the first occurrence of l in the string
print(string_2) #if not found, returns -1

string_3 = "Hello World"
print(string_3.count("l")) # 3; counts the number of times l appears in the string

string_3 = string_3.replace("World", "Universe") # replaces World with Universe; if not found, returns original string
print(string_3) # Hello Universe; returns a new string, original string is unchanged



# String and lists
string_4 = "how are you doing"
list_1 = string_4.split(" ") # splits the string into a list of strings, using space as the delimiter
print(list_1) # ['how', 'are', 'you', 'doing']

new_string = " ".join(list_1) # joins the list of strings into a string, using space as the delimiter
print(new_string) # how are you doing

list_2 = ["a"] * 6
print(list_2) # ['a', 'a', 'a', 'a', 'a', 'a']

string_5 = ""
for i in list_2:
    string_5 += i + " " # adds each element in the list to the string, with a space in between
print(string_5) # a a a a a a  ; inefficient, better to use join

string_6 = " ".join(list_2)
print(string_6) # a a a a a a ; more efficient than the for loop above



# Formatting strings %, .format(), f-Strings
var = "Tom"
string_7 = "the variable is %s" % var # %s is a placeholder for the variable
print(string_7) # the variable is Tom

var = 3
string_7 = "the variable is %d" % var # %d is a placeholder for the integer variable
print(string_7) # the variable is 3

var = 3.1234567
string_7 = "the variable is %.2f" % var # %.2f is a placeholder for the float variable, with 2 decimal places
print(string_7) # the variable is 3.12

var = 3.1234567
string_7 = "the variable is {}".format(var) # {} is a placeholder for the float variable, with 2 decimal places
print(string_7) # the variable is 3.1234567

var = 3.1234567
var2 = 6
string_7 = "the variable is {:.2f} and {}".format(var, var2) # {} is a placeholder for the float variable, with 2 decimal places
print(string_7) # the variable is 3.12 and 6

var = 3.1234567
var2 = 6
string_7 = f"the variable is {var} and {var2}" # {} is a placeholder for the float variable, with 2 decimal places
print(string_7) # the variable is 3.1234567 and 6

string_7 = f"the variable is {var*3} and {var2:.2f}" # {} evaluates the expression inside in runtime
print(string_7) # the variable is 9.3703701 and 6.00
```
<br/>
<br/>

## 6. Collections
[🔼 Back to top](#content)
```Python
# collections: Counter, namedtuple, OrderedDict, defaultdict, deque

from collections import Counter
# Counter is container that stores elements as dictionary keys, and their counts are stored as dictionary values.

a = "aaaaabbbbccc"
my_counter = Counter(a)
print(my_counter) # Counter({'a': 5, 'b': 4, 'c': 3})

print(my_counter.items()) # dict_items([('a', 5), ('b', 4), ('c', 3)])
print(my_counter.keys()) # dict_keys(['a', 'b', 'c'])
print(my_counter.values()) # dict_values([5, 4, 3])

print(my_counter.most_common(1)) # [('a', 5)] # returns the most common element
print(my_counter.most_common(2)) # [('a', 5), ('b', 4)] # returns the 2 most common elements

print(my_counter.most_common(1)[0][0]) # a # returns the most common element
 
print(list(my_counter.elements())) # ['a', 'a', 'a', 'a', 'a', 'b', 'b', 'b', 'b', 'c', 'c', 'c']



from collections import namedtuple
# namedtuple is a container with a name for each value
Point = namedtuple('Point', 'x,y')
pt = Point(1, -4)
print(pt) # Point(x=1, y=-4)

print(pt.x, pt.y) # 1 -4


from collections import OrderedDict
# OrderedDict is a dictionary subclass that remembers the order in which its contents are added
ordered_dict = OrderedDict()
ordered_dict['a'] = 1
ordered_dict['b'] = 2
ordered_dict['c'] = 3
ordered_dict['d'] = 4
print(ordered_dict) # OrderedDict([('a', 1), ('b', 2), ('c', 3), ('d', 4)])
# from python 3.7, the default dictionary is orderedfrom

from collections import defaultdict
d = defaultdict(int) # float, list, str, etc not key error if the key is not in the dictionary
d['a'] = 1
d['b'] = 2
print(d['a']) # 1
print(d['c']) # 0 # returns 0 if the key is not in the dictionary


from collections import deque
# deque is a double-ended queue that allows you to add and remove elements from both ends
d = deque()

d.append(1)
d.append(2)
print(d) # deque([1, 2])

d.appendleft(3)
print(d) # deque([3, 1, 2])

d.pop()
print(d) # deque([3, 1])

d.popleft()
print(d) # deque([1])

d.clear()
print(d) # deque([])

d.extend([4, 5, 6])
print(d) # deque([4, 5, 6])

d.extendleft([1, 2, 3])
print(d) # deque([3, 2, 1, 4, 5, 6])

d.rotate(1)
print(d) # deque([6, 3, 2, 1, 4, 5])

d.rotate(2)
print(d) # deque([4, 5, 6, 3, 2, 1])

d.rotate(-1)
print(d) # deque([5, 6, 3, 2, 1, 4])
```
<br/>
<br/>

## 7. Itertools
[🔼 Back to top](#content)
```Python
# itertools: product, permutations, combinations, accumulate, groupby, and infinite iterators
# collection of tools for handling iterators; functions that operate on iterators to produce more complex iterators


from itertools import product
a = [1, 2]
b = [3, 4]
prod = product(a, b) # cartesian product of a and b
print(list(prod)) # [(1, 3), (1, 4), (2, 3), (2, 4)]


b = [3]
prod = product(a, b, repeat=2) # cartesian product of a and b, repeat=2 means repeat twice
print(list(prod)) # [(1, 3, 1, 3), (1, 3, 2, 3), (2, 3, 1, 3), (2, 3, 2, 3)]


from itertools import permutations
#returns all possible orderings of an input
a = [1, 2, 3]
perm = permutations(a)
print(list(perm)) # [(1, 2, 3), (1, 3, 2), (2, 1, 3), (2, 3, 1), (3, 1, 2), (3, 2, 1)]

perm = permutations(a, 2) # 2 means the length of the permutation
print(list(perm)) # [(1, 2), (1, 3), (2, 1), (2, 3), (3, 1), (3, 2)]


from itertools import combinations, combinations_with_replacement
#returns all possible combinations of an input
a = [1, 2, 3, 4]
comb = combinations(a, 2) # 2 means the length of the combination
print(list(comb)) # [(1, 2), (1, 3), (1, 4), (2, 3), (2, 4), (3, 4)] # no repeats

comb_wr = combinations_with_replacement(a, 2) # 2 means the length of the combination
print(list(comb_wr)) # [(1, 1), (1, 2), (1, 3), (1, 4), (2, 2), (2, 3), (2, 4), (3, 3), (3, 4), (4, 4)] # repeats




from itertools import accumulate
import operator
#returns accumulated sums
a = [1, 2, 3, 4]
acc = accumulate(a)
print(a) # [1, 2, 3, 4]
print(list(acc)) # [1, 3, 6, 10]

acc = accumulate(a, func=operator.mul) # multiply instead of add
print(list(acc)) # [1, 2, 6, 24]

b = [1, 2, 5, 3, 4]
acc = accumulate(b, func=max) # max instead of add
print(list(acc)) # [1, 2, 5, 5, 5]




from itertools import groupby
#groups consecutive elements together based on a given key
def smaller_than_3(x):
    return x < 3

a = [1, 2, 3, 4]
group_obj = groupby(a, key=smaller_than_3) # key is a function that takes a single value as an argument and returns a key
for key, value in group_obj:
    print(key, list(value)) # True [1, 2] # False [3, 4]

#lambda function is a small anonymous function
group_obj = groupby(a, key=lambda x: x < 3)
for key, value in group_obj:
    print(key, list(value)) # True [1, 2] # False [3, 4]

persons = [{'name': 'Tim', 'age': 25}, {'name': 'Dan', 'age': 25}, 
           {'name': 'Lisa', 'age': 27}, {'name': 'Claire', 'age': 28}]

group_obj = groupby(persons, key=lambda x: x['age'])
for key, value in group_obj:
    print(key, list(value)) # 25 [{'name': 'Tim', 'age': 25}, {'name': 'Dan', 'age': 25}] 
                            # 27 [{'name': 'Lisa', 'age': 27}] 
                            # 28 [{'name': 'Claire', 'age': 28}]


from itertools import count, cycle, repeat
#count: counts up infinitely from a value
for i in count(10):
    print(i)
    if i == 15:
        break # 10 11 12 13 14 15

#cycle: infinitely iterates through an iterable (for loop)
a = [1, 2, 3]
for i in cycle(a):
    print(i) # infinite loop
    break # 1 2 3


for i in repeat(1, 4): # repeat 1 four times; will not be an infinite loop
    print(i) # 1 1 1 1
```
<br/>
<br/>

## 8. Lambda Functions
[🔼 Back to top](#content)
```Python
# lambda arguments: expression <----syntax (small, one  line anonymous function)

add10 = lambda x: x + 10
print(add10(5)) # 15

def add10_func(x):
    return x + 10

mult = lambda x, y: x * y
print(mult(2, 7)) # 14

# used  when you need a function for a short period of time


#sorted
points2D = [(1, 2), (15, 1), (5, -1), (10, 4)]
points2D_sorted = sorted(points2D)
print(points2D) # [(1, 2), (15, 1), (5, -1), (10, 4)]'
print(points2D_sorted) # [(1, 2), (5, -1), (10, 4), (15, 1)]
# sort by x

points2D = [(1, 2), (15, 1), (5, -1), (10, 4)]
points2D_sorted = sorted(points2D, key=lambda x: x[1])
print(points2D_sorted) # [(5, -1), (15, 1), (1, 2), (10, 4)]
# sort by y

def sort_by_y(x):
    return x[1]

points2D = [(1, 2), (15, 1), (5, -1), (10, 4)]
points2D_sorted = sorted(points2D, key=lambda x: x[0] + x[1])
print(points2D_sorted) # [(1, 2), (5, -1), (10, 4), (15, 1)]
# sort by sum of x and y


# map(func, seq)
a = [1, 2, 3, 4, 5]
b = map(lambda x: x * 2, a)
print(list(b)) # [2, 4, 6, 8, 10]
# map each element of a to x * 2

c = [x * 2 for x in a]  # list comprehension same as map


# filter(func, seq)
a = [1, 2, 3, 4, 5, 6]
b = filter(lambda x: x % 2 == 0, a)
print(list(b)) # [2, 4, 6]
# filter out odd numbers

c = [x for x in a if x % 2 == 0] # list comprehension same as filter

# reduce(func, seq)
from functools import reduce
a = [1, 2, 3, 4,]

product_a = reduce(lambda x, y: x * y, a)
print(product_a) # 24
# multiply all numbers in a
```
<br/>
<br/>

## 9. Exceptions and Errors
[🔼 Back to top](#content)
```Python
# Errors and Exceptions

# Syntax Errors - also known as parsing errors

a = 5 print(a) # SyntaxError: invalid syntax

a=5
print(a)) # SyntaxError: unmatched ')'

a = 5 + '10' # TypeError: unsupported operand type(s) for +: 'int' and 'str'

import somemodule # ModuleNotFoundError: No module named 'somemodule'

b = c # NameError: name 'c' is not defined

f = open('somefile.txt') # FileNotFoundError: [Errno 2] No such file or directory: 'somefile.txt'

a = [1, 2, 3]
a.remove(4) # ValueError: list.remove(x): x not in list

my_dict = {'name': 'Max'}
my_dict['age'] # KeyError: 'age'


X = -5
if X < 0:
    raise Exception('X should be positive') # Exception: X should be positive

x = -5
assert (x >= 0), 'x is not positive' # AssertionError: x is not positive




# try except else finally
try:
    a = 5 / 0
except:
    print('an error happened') #program continues


try:
    a = 5 / 0
except Exception as e:
    print(e) #division by zero


try:
    a = 5 / 0
    b = a + '10'
except ZeroDivisionError as e:
    print(e)
except TypeError as e:
    print(e)
else:
    print('everything is fine') #else runs if no exception
finally:
    print('cleaning up...') #finally always runs





# Custom Exceptions
class ValueTooHighError(Exception):
    pass

class ValueTooSmallError(Exception):
    def __init__(self, message, value):
        self.message = message
        self.value = value

def test_value(x):
    if x > 100:
        raise ValueTooHighError('value is too high')

    if x < 5:
        raise ValueTooSmallError('value is too small', x)


try:
    test_value(2)
except ValueTooHighError as e:
    print(e)
except ValueTooSmallError as e:
    print(e.message, e.value) #we can access the attributes of the exception





```
<br/>
<br/>


## 10. Logging 
[🔼 Back to top](#content)

The logging module in Python is a powerful built-in module so you can quickly add logging to your application.  
`import logging`
## Log Level <!-- omit in toc -->
There are 5 different log levels indicating the serverity of events. By default, the system logs only events with level *WARNING* and above.

```Python
import logging
logging.debug('This is a debug message')
logging.info('This is an info message')
logging.warning('This is a warning message')
logging.error('This is an error message')
logging.critical('This is a critical message')
```
## Configuration
With `basicConfig(**kwargs)` you can customize the root logger. The most common parameters are the *level*, the *format*, and the *filename*. See https://docs.python.org/3/library/logging.html#logging.basicConfig for all possible arguments. See also https://docs.python.org/3/library/logging.html#logrecord-attributes for possible formats and https://docs.python.org/3/library/time.html#time.strftime how to set the time string. Note that this function should only be called once, and typically first thing after importing the module. It has no effect if the root logger already has handlers configured. For example calling `logging.info(...)` before the *basicConfig* will already set a handler.
```Python
import logging
logging.basicConfig(level=logging.DEBUG, format='%(asctime)s - %(name)s - %(levelname)s - %(message)s', datefmt='%m/%d/%Y %H:%M:%S')
# Now also debug messages will get logged with a different format.
logging.debug('Debug message')

# This would log to a file instead of the console.
# logging.basicConfig(level=logging.DEBUG, filename='app.log')
```
## Logging in modules and logger hierarchy
Best practice in your application with multiple modules is to create an internal logger using the `__name__` global variable. This will create a logger with the name of your module and ensures no name collisions. The logging module creates a hierarchy of loggers, starting with the root logger, and adding the new logger to this hierarchy. If you then import your module in another module, log messages can be associated with the correct module through the logger name. Note that changing the basicConfig of the root logger will also affect the log events of the other (lower) loggers in the hierarchy.

```Python
# helper.py
# -------------------------------------
import logging
logger = logging.getLogger(__name__)
logger.info('HELLO')

# main.py
# -------------------------------------
import logging
logging.basicConfig(level=logging.INFO, format='%(name)s - %(levelname)s - %(message)s')
import helper

# --> Output when running main.py
# helper - INFO - HELLO
```
## Propagation
By default, all created loggers will pass the log events to the handlers of higher loggers, in addition to any handlers attached to the created logger. You can deactivate this by setting `propagate = False`. Sometimes when you wonder why you don't see log messages from another module, then this property may be the reason.
```Python
# helper.py
# -------------------------------------
import logging
logger = logging.getLogger(__name__)
logger.propagate = False
logger.info('HELLO')

# main.py
# -------------------------------------
import logging
logging.basicConfig(level=logging.INFO, format='%(name)s - %(levelname)s - %(message)s')
import helper

# --> No output when running main.py since the helper module logger does not propagate its messages to the root logger
```
## LogHandlers
Handler objects are responsible for dispatching the appropriate log messages to the handler's specific destination. For example you can use different handlers to send log messaged to the standard output stream, to files, via HTTP, or via Email. Typically you configure each handler with a level (`setLevel()`), a formatter (`setFormatter()`), and optionally a filter (`addFilter()`). See https://docs.python.org/3/howto/logging.html#useful-handlers for possible built-in handlers. Of course you can also implement your own handlers by deriving from these classes.
```Python
import logging

logger = logging.getLogger(__name__)

# Create handlers
stream_handler = logging.StreamHandler()
file_handler = logging.FileHandler('file.log')

# Configure level and formatter and add it to handlers
stream_handler.setLevel(logging.WARNING) # warning and above is logged to the stream
file_handler.setLevel(logging.ERROR) # error and above is logged to a file

stream_format = logging.Formatter('%(name)s - %(levelname)s - %(message)s')
file_format = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
stream_handler.setFormatter(stream_format)
file_handler.setFormatter(file_format)

# Add handlers to the logger
logger.addHandler(stream_handler)
logger.addHandler(file_handler)

logger.warning('This is a warning') # logged to the stream
logger.error('This is an error') # logged to the stream AND the file!
```
#### Example of a filter
```Python
class InfoFilter(logging.Filter):
    
    # overwrite this method. Only log records for which this
    # function evaluates to True will pass the filter.
    def filter(self, record):
        return record.levelno == logging.INFO

# Now only INFO level messages will be logged
stream_handler.addFilter(InfoFilter())
logger.addHandler(stream_handler)
```
## Other configuration methods
We have seen how to configure logging creating loggers, handlers, and formatters explicitely in code. There are two other configration methods:
- Creating a logging config file and reading it using the `fileConfig()` function. See example below.
- Creating a dictionary of configuration information and passing it to the `dictConfig()` function. See https://docs.python.org/3/library/logging.config.html#logging.config.dictConfig for more information.

#### .conf file
Create a *.conf* (or sometimes stored as *.ini*) file, define the loggers, handlers, and formatters and provide the names as keys. After their names are defined, they are configured by adding the words *logger*, *handler*, and *formatter* before their names separated by an underscore. Then you can set the properties for each logger, handler, and formatter. In the example below, the root logger and a logger named *simpleExample* will be configured with a StreamHandler.
```Python
# logging.conf
[loggers]
keys=root,simpleExample

[handlers]
keys=consoleHandler

[formatters]
keys=simpleFormatter

[logger_root]
level=DEBUG
handlers=consoleHandler

[logger_simpleExample]
level=DEBUG
handlers=consoleHandler
qualname=simpleExample
propagate=0

[handler_consoleHandler]
class=StreamHandler
level=DEBUG
formatter=simpleFormatter
args=(sys.stdout,)

[formatter_simpleFormatter]
format=%(asctime)s - %(name)s - %(levelname)s - %(message)s
```
```Python
# Then use the config file in the code
import logging
import logging.config

logging.config.fileConfig('logging.conf')

# create logger with the name from the config file. 
# This logger now has StreamHandler with DEBUG Level and the specified format
logger = logging.getLogger('simpleExample')

logger.debug('debug message')
logger.info('info message')`
```
## Capture Stack traces
Logging the traceback in your exception logs can be very helpful for troubleshooting issues. You can capture the traceback in *logging.error()* by setting the *exc_info* parameter to True.
```Python
import logging

try:
    a = [1, 2, 3]
    value = a[3]
except IndexError as e:
    logging.error(e)
    logging.error(e, exc_info=True)
```
If you don't capture the correct Exception, you can also use the *traceback.format_exc()* method to log the exception.
```Python
import logging
import traceback

try:
    a = [1, 2, 3]
    value = a[3]
except:
    logging.error("uncaught exception: %s", traceback.format_exc())
```
## Rotating FileHandler
When you have a large application that logs many events to a file, and you only need to keep track of the most recent events, then use a RotatingFileHandler that keeps the files small.
When the log reaches a certain number of bytes, it gets "rolled over". You can also keep multiple backup log files before overwriting them.
```Python
import logging
from logging.handlers import RotatingFileHandler

logger = logging.getLogger(__name__)
logger.setLevel(logging.INFO)

# roll over after 2KB, and keep backup logs app.log.1, app.log.2 , etc.
handler = RotatingFileHandler('app.log', maxBytes=2000, backupCount=5)
logger.addHandler(handler)

for _ in range(10000):
    logger.info('Hello, world!')
```
## TimedRotatingFileHandler
If your application will be running for a long time, you can use a TimedRotatingFileHandler. This will create a rotating log based on how much time has passed. Possible time conditions for the *when* parameter are:
- second (s)
- minute (m)
- hour (h)
- day (d)
- w0-w6 (weekday, 0=Monday)
- midnight
```Python
import logging
import time
from logging.handlers import TimedRotatingFileHandler
 
logger = logging.getLogger(__name__)
logger.setLevel(logging.INFO)

# This will create a new log file every minute, and 5 backup files with a timestamp before overwriting old logs.
handler = TimedRotatingFileHandler('timed_test.log', when='m', interval=1, backupCount=5)
logger.addHandler(handler)
 
for i in range(6):
    logger.info('Hello, world!')
    time.sleep(50)`
```
# Logging in JSON Format
If your application generates many logs from different modules, and especially in a microservice architecture, it can be challenging to locate the important logs for your analysis. Therefore, it is best practice to log your messages in JSON format, and send them to a centralized log management system. Then you can easily search, visualize, and analyze your log records.  
I would recommend using this Open Source JSON logger: https://github.com/madzak/python-json-logger  
`pip install python-json-logger`
```Python
import logging
from pythonjsonlogger import jsonlogger

logger = logging.getLogger()

logHandler = logging.StreamHandler()
formatter = jsonlogger.JsonFormatter()
logHandler.setFormatter(formatter)
logger.addHandler(logHandler)****
```
<br/>
<br/>

## 11. Next
[🔼 Back to top](#content)
```Python

```
<br/>
<br/>
