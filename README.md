# python-cheatsheet

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

```
string.split("separator", maxsplit) 
```
The split() method splits a string into a list.  
The separator specifies the separator to use when splitting the string. By default, any whitespace is a separator. The maxsplit specifies how many splits to do. The default for that it -1, which is "all occurances."  

## hasattr() syntax:
```
hasattr(object, attribute) 
```
The hasattr() function returns True if the specified object has the specified attribute, otherwise it returns False. The object is required and the attribute is the name of the attribute you want to check exists. You can also use `"__iter__"`.  

## Python min() and max() in List or Array
```
min(myList)
max(myList)
```
Returns the largest and smallest items in a list or array ([docs](https://docs.python.org/3/library/functions.html#max)).


## Python enumerate() function
```
x = ['apple', 'banana', 'cherry']
for index, value in enumerate(x):
	print(f'index: {index}, value: {value}')
```  
Converts an iterable (list, tuple, string, etc) into an enumerated object, which contains a counter value. Essentially, it assigns a counter value (0, 1, 2, 3) to each value in the iterable. Can be used with a `for each` to get the index, as well as the value, in the sequence ([docs](https://www.w3schools.com/python/ref_func_enumerate.asp)).