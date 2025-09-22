# Note for first 20 days

In this section , there are these new things :

## 1. tuple && dict && set && list

### 1) list:

**list [ ]** has more ways of initialization

- list comprehension  : `a = [ x*x  for x in range(5)] `
- generator || function : `ls = list (range(5))`
- `slice` syntax : `list[start:end:step]`
### 2) tuple:

**tuple( )** is not changeable , but it is faster than list to generate

### 3) set : 

almost the same as it is in cpp , no iterator anymore

### 4） dict : 

**dict** is just like the  **unordered_map** in cpp

---

---

## 2. CLASS

Here are something different from C++:

- use `__init__(para)` as constructor
- use `__repr__(self)` to customize `print`
- the functions in it should obtain an extra para `self` as the class itself
--- 
- for member variables , `__private` , `_protected`
- use `@staticmethod` `@classmethod` to call the functions from the class perspective
- use `@property` to transform function into property
- also as a dynamic language , python allows us to **add extra property outside the object def** , we can use `__slots__` to prevent this situation
---
- inherit : use `super().__init()__` inside the constructor
- for `virtual function` in cpp , python use `@abstractmethod` `def` `pass`