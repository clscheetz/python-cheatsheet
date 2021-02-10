# python-cheatsheet

## Lists, Sets, Tuples, Dictionaries
A [list] is the simplest data structure, used to store a list of values. Lists are enclosed with [ ] and each item in the list has an assigned index. Lists are mutable (changeable) and each item in the list is serparated by a comma. 

A (tuple) is a sequence of values, much like a list. They can store any data type, like lists, and are indexed by integers. It's important to remember that tuples are immutable (unable to be changed).

Sets are unorderd and can be modified, but the elements contained in the set must be of an immutable type. Elements of a set are unique and duplicate elements are not allowed. They can perform mathematical set operations like union, intersection, symmetric difference, etc. 

A {dictionary} is a collection of key-value pairs and you use [ ] to index over it. Separate the key and value with colons: and with commas, between each pair. Keys must be quoted, and you can print the dictionary by printing the reference to it. A dictionary maps a set of objects (keys) to another set of objects (values). Dictionaries are unordered and are muttable (changeable). 

Both lists and dictionaries are mutable, dynamic, and can be nested. A list can contain another list. A dictionary can contain another dictionary. A dictionary can also contain a list, and vice versa. List elements are accessed by their position in the list, via indexing and dictionary elements are accessed vis keys. ([docs](https://medium.com/@nishantbhushan10/python-lists-tuples-sets-dictionary-a9cbcac183e3)).

## Escape Characters

|Code|Result|
|----|-----|
|\\'|Single Quote|
| \\\\ |Backslash|
|\n| New Line|
|\r| Carriage Return|
|\t| Tab|
|\b| Backspace|
|\f| Form Feed|
|\ooo| Octal Value|
|\xhh| Hex Value|   


## String split() syntax:   

```py
string.split("separator", maxsplit) 
```
The split() method splits a string into a list.  
The separator specifies the separator to use when splitting the string. By default, any whitespace is a separator. The maxsplit specifies how many splits to do. The default for that it -1, which is "all occurances."  

## hasattr() syntax:
```py
hasattr(object, attribute) 
```
The hasattr() function returns True if the specified object has the specified attribute, otherwise it returns False. The object is required and the attribute is the name of the attribute you want to check exists. You can also use `"__iter__"`.  

## min() and max() in List or Array
```py
min(myList)
max(myList)
```
Returns the largest and smallest items in a list or array ([docs](https://docs.python.org/3/library/functions.html#max)).


## enumerate() function
```py
x = ['apple', 'banana', 'cherry']
for index, value in enumerate(x):
	print(f'index: {index}, value: {value}')
```  
Converts an iterable (list, tuple, string, etc) into an enumerated object, which contains a counter value. Essentially, it assigns a counter value (0, 1, 2, 3) to each value in the iterable. Can be used with a `for each` to get the index, as well as the value, in the sequence ([docs](https://www.w3schools.com/python/ref_func_enumerate.asp)).

## dict.fromkeys() funtion
```py
mylist = ["a", "b", "a", "c", "c"]
mylist = list(dict.fromkeys(mylist))
print(mylist)
```
The `dict.fromkeys()` reads every entry in the list and places them as keys in a returned dictionary. Any duplicate keys are ignored because dictionaries can't have duplicate keys.

## map() function
```py
map(funtion, iterable)
```
The map function applies the given function to each item in the given iterable (list, tuple, dict, sets) and returns a map object (which is an iterator). Since it returns a map object, you may have to cast it to an iterable (list, set). Ex: `list(map(set, words))`
