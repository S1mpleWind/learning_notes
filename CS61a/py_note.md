# Note for CS61A

## Iterator
 
Iterator works like a pointer pointing to the elements in a container ,  
we can use `iter(container)` to initialize a iterator , and it will start execute when calling it

Moreover , `map` and `filter` function return a **iterator** . That is to say these functions are not operated until u call and renew the iterators , they r **lazy** functions

---

## Generator 

### Basics

Actually `generator function` also return a `iterator`  
Let's say that *generator* is a function that `yield`s values instead of returning values  
And a generator function can *yield* multiple times

eg.

```python
def plus_minus(x):
    yield x
    yield -x

t = plus_minus(3)
next(t) # get 3
next(t) # get 3
```

another example

```python
def evens(start,end):
    even = start + start%2 # make sure starting from even
    while even < end:
        yield even
        even+=2
```

### More

We can do more things with *generator* like initializing a list using it

```python
def count_down(n):
    if n>0 :
        yield n
        yield from count_down (n-1)
        # use 'from' to get values within a generator
    
ls = list [count_down(7)]
```

partition example using generator

```python
def partition(n,m):
    '''part n into smaller nums that are <= m'''
    #base case :
    if n>0 and m>0:

        # outing situation
        if n == m :
            yield str(m)
        
        # current level operation : recursive call
        for p in partition(n-m,m):
            yield p + '+' + str(m)
        
        yield from partition(n,m-1)
```

---

## Objects 

Here are something different from C++:

1. Init / Construct

    - use `__init__(para)` as constructor
    - use `__repr__(self)` to customize `print`
    - the functions in it should obtain an extra para `self` as the class itself

2. Permission

    - for member variables , `__private` , `_protected`
    - use `@staticmethod` `@classmethod` to call the functions from the class perspective
    - use `@property` to transform function into property
    - also as a dynamic language , python allows us to **add extra property outside the object def** , we can use `__slots__` to prevent this situation

3. Attribute
    - `getattr` has the same func as *dot expression*
    - `hasattr` can check whether an attribute exist or not
    - create `Class Attribute` outside of constructor  ; If there are class attributes and instance attributes sharing the same name , python will look for the **instance one** first

    ```python
    class account :
        interest = 0.02 # this is a class attribute

        def __init__(self,account_holder):
            self.balance = 0
            self,holder = account_holder # Instance Attribute
    ```

4. Inherit
    - inherit : use `super().__init()__` inside the constructor
    - for `virtual function` in cpp , python use `@abstractmethod` `def` `pass`

