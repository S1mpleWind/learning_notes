# Note for Day 21-30
## File operation
use `open` function in python to do all the file stuff
```python
file = open ("helloworld.txt","r",encoding='utf-8')
'''para : filename , option , encoding'''

'''other functions includes: read() , close() , write() , readlines()'''
'''member variable includes: line'''
``` 

---

## Exception handling
use `try` `except` `finally` to catch and handle exceptions  
use `raise` to throw a exception

python contains many types of exceptions , we can also define our own
```python
class InputError(ValueError):
    """customize a error , inherit from valuerror"""
    pass
```

---

## `With` syntax
by using `with` , we don't need to close file by hand in `finally`
```python
file = None
try:
    with open("helloworld.txt",'r') as file :
        print(file.read())
except FileNotFoundError :
    print("cannot find the wanted file")
```
---

## JSON
|   |  | |  |  |   | |
|----|---|---|---|--|---|---|
|JSON | object | array | string | number| null |
|Python | dict | list  | str | int/float | None |
 in module `json` :

- dump : py object -> json data
- dumps: py object -> json string
- load : json data -> py object
- loads:   string  -> py object

## CSV
define a `csvwriter` object to write data into csv file
```python
import csv
with open('test.csv','w') as file:
    writer = csv.writer(file)
    writer.writerow('','','')
```

also , we can create a `csvreader` object to read data from a csv file
```python
import csv
with open('read.csv','r') as file:
    reader = csv.reader(file,delimiter='|')
    
# learn more about it when needed
```

## Excel
use third-party library `xlwt``xlrd`
**learn it when needed**

## Regular Expression
use this to judge how to match our search for string
use `re` module to handle this situation . 
**learn when needed**
