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