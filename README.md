# python-cheatsheet

# Collections of data

## Lists

A [list] is the simplest data structure, used to store a list of values. Lists are enclosed with [ ] and each item in the list has an assigned index. Lists are mutable (changeable) and each item in the list is serparated by a comma. 

## Tuples

A (tuple) is a sequence of values, much like a list. They can store any data type, like lists, and are indexed by integers. It's important to remember that tuples are immutable (unable to be changed).

## Sets

Sets `{}` or `set()` are unorderd and can be modified, but the elements contained in the set must be of an immutable type. Elements of a set are unique and duplicate elements are not allowed. They can perform mathematical set operations like union, intersection, symmetric difference, etc. The elements of a set MUST be hashable, meaning the `__hash__()` fuction must be callable on the item you are trying to add. For example, dictionaries are not hashable.

## Dictionaries

A {dictionary} is a collection of key-value pairs and you use [ ] to index over it. Separate the key and value with colons: and with commas, between each pair. Keys must be quoted, and you can print the dictionary by printing the reference to it. A dictionary maps a set of objects (keys) to another set of objects (values). Dictionaries are unordered and are muttable (changeable). 

Both lists and dictionaries are mutable, dynamic, and can be nested. A list can contain another list. A dictionary can contain another dictionary. A dictionary can also contain a list, and vice versa. List elements are accessed by their position in the list, via indexing and dictionary elements are accessed vis keys. ([docs](https://medium.com/@nishantbhushan10/python-lists-tuples-sets-dictionary-a9cbcac183e3)).

## Hash Examples

| Hash Call | Hash Output |
| --------- | ----------- |
| `int(1).__hash__()` | 1 |
| `True.__hash__()` | 1 |
| `float(1.0).__hash__()` | 1 |

_Notice each of these return the same hash value, meaning they evaluate as equal. For example: `True == 1`_  

```py
>>> {1, 1.0, True}
{1}
>>> {True, 1.0, 1}
{True}
```
_Notice that the set only contains the first entry because each of their hash vales are the same. It should be noted that duplicate values are ignored._

When adding items to a set, the set hashes the value to use for lookup later. When two items identify with the same hash, only one is kept. In other words, the set's uniqueness of items is determined by their hash values.

The reasoning for the set storing hashes is that it is faster to make equality comparisons with integer values. The set only needs to hash the values on initial entry.

## Escape Characters

|Code|Result|
|----|-----|
|`\'`|Single Quote|
| `\\` |Backslash|
|`\n`| New Line|
|`\r`| Carriage Return|
|`\t`| Tab|
|`\b`| Backspace|
|`\f`| Form Feed|
|`\ooo`| Octal Value|
|`\xhh`| Hex Value|   


## String `split()` syntax:   

```py
string.split("separator", maxsplit) 
```
The split() method splits a string into a list.  
The separator specifies the separator to use when splitting the string. By default, any whitespace is a separator. The maxsplit specifies how many splits to do. The default for that it -1, which is "all occurances."  

## `hasattr()` syntax:
```py
hasattr(object, attribute) 
```
The hasattr() function returns True if the specified object has the specified attribute, otherwise it returns False. The object is required and the attribute is the name of the attribute you want to check exists. You can also use `"__iter__"`.  

## `min()` and `max()` in List or Array
```py
min(myList)
max(myList)
```
Returns the largest and smallest items in a list or array ([docs](https://docs.python.org/3/library/functions.html#max)).

## `enumerate()` function
```py
>>> x = ['apple', 'banana', 'cherry']
>>> for index, value in enumerate(x):
...     print(f'index: {index}, value: {value}')
...
index: 0, value: apple
index: 1, value: banana
index: 2, value: cherry
```  
Converts an iterable (list, tuple, string, etc) into an enumerated object, which contains a counter value. Essentially, it assigns a counter value (0, 1, 2, 3) to each value in the iterable. Can be used with a `for each` to get the index, as well as the value, in the sequence ([docs](https://www.w3schools.com/python/ref_func_enumerate.asp)).

## `dict.fromkeys()` funtion
```py
>>> myList = ["a", "b", "a", "c", "c"]
>>> myList = list(dict.fromkeys(myList))
>>> print(myList)
['a', 'b', 'c']
```
The `dict.fromkeys(<list>)` reads every entry in the list and places them as keys in a returned list. Any duplicate keys are ignored as dictionaries do not have duplicate keys.

## `dict.get()` function 
```py
my_dict.get(keyname, value) 

>>> new_dict.get('name', 'hi')
'hi'
```
keyname =  	Required. The key(name) of the item you want to return the value from. If it does not exist in the dict, return `'hi'`.

value = Optional. A value to return if the specified key does not exist.
Default value `None`.

## `map()` function
```py
map(funtion, iterable)
```
The map function applies the given function to each item in the given iterable (list, tuple, dict, sets) and returns a map object (which is an iterator). Since it returns a map object, you may have to cast it to an iterable (list, set). Ex: `list(map(set, words))`

## `.remove()` method
```py
list.remove(element)
```
The remove method removes the FIRST matching element, which is passed as an argument, from the list. It will ONLY remove ONE element, which is the FIRST matching element. If you need to remove multiple of the same element, you will need to loop through the list. See the 2nd example under list comprehension down below. 

## `.format()` method
The format method formats the specified value(s), inserts them inside the string's placeholder, and then returns the formatted string. The placeholder is defines using curly brackets{}. They can be named, numbered, or left empty.
```py
"My name is {fname} and I'm {age}.".format(fname = "Chelsea", age = 32)
"My name is {0}, I'm {1}.".format("Chelsea",32)
"My name is {} and I'm {}.".format("Chelsea",32)
```

## `f-strings` in Python

## `zip()` 
The `zip()` funtion returns a zip object, which is an iterator of tuples where the first item in each passed iterator is paired together, and then the second items are paired, and so on...

If the passed iterators have different lengths, the iterator with the fewest items decides the length of the new iterator.

```py
a = [1, 2, 3]
b = ['a', 'b', 'c', 'd'] #see below that 'd' is left off
list(zip(a,b))

>>> [(1, 'a'), (2, 'b'), (3, 'c')]
```

## List Comprehensions 
Allows you to filter and transform ANY iterable into a list. You can iterate over an existing list, but it will create an entirely new list. 

The conditional is evaluated first (optional) prior to the transformation. A list comprehension is essentially an in-line for loop. 

```py
#Using list comprehension, take a string & create a list making all characters capitalized and 
#separated.

myName = 'Chelsea'
nameSeparated = [letter.upper() for letter in myName if letter != 'e']
print(nameSeparated)

>>> ['C', 'H', 'L', 'S', 'A']
```
```py
#Complete the function remove_all(L, x) so that, given a list L and a target value x, it returns a 
#copy of the list that excludes all occurrences of x but preserves the order of the remaining elements.

 results = []
    for num in L:
        if num != x:
            results.append(num)
    return results

    #THE BETTER SOLUTION IS USING LIST COMPREHENSION***
    
[num for num in L if num != x]

>>> Testing remove_all function: ([1, 2, 3, 2, 4, 8, 2], 2)...
	True solution: [1, 3, 4, 8]
	Your computed solution: [1, 3, 4, 8]
```
