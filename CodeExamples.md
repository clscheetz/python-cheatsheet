### Implement dict.get() function
```py
my_dict = {'name': 'Chelsea', 'age': 31}

def get(self, key, default=None):
    if self.__contains__(key):
        return self[key]
    else:
        return default

#Calling the get function that I implemented
value = get(my_dict, "email")
print(value)
```
