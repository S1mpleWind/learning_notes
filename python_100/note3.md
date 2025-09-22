# Note for 31-35 days here

## Little Syntax

`pass` has a similar function like `virtual` in c++ , it is an empty sentence to make *explaination* work

## **Backtracking** Thinkway

backtracking is like **try and go back** way in a recursive call  
we assume there r 2 conditions : `legal_process` , `legal_result`  
and in the current process we have to do a `current_operation`

```txt
function backtracking()
{
    if ( legal_process ) 
    {
        do current_operation ;
        
        if( legal_result )
            {
                handle the result
            }
        
        else
        {
            recursive call function
        }    
        
        backtrack current_operation
    }
}
```

typical example : *knight Patrol*

---

## Decorate function

decorate funcition is like adding clothes to your funciton 

eg.

```python
def my_decorator(func):
    '''give a decorator '''
    def wrapper(*args,**kwargs):
        print ("before wrapping")
        result = func(*args,**kwargs)
        print ("after wrapping")
        return result
    return wrapper

@my_decorator
# equals to hello = my_decorator(hello)

def hello( name ):
    printf('hello' + name )
```

however in this way the origin function is renamed to `wrapper`

To keep the name and comments in the function , we can use module `functools`

```python
def record_time(func):
    """自定义装饰函数的装饰器"""
    
    @wraps(func)
    # here wraps can help C-O-P-Y the name and property of the original function
    def wrapper(*args, **kwargs):
        start = time()
        result = func(*args, **kwargs)
        print(f'{func.__name__}: {time() - start}秒')
        return result
        
    return wrapper
```

---

## Garbage Collection

py manages memory automatically , and use a `ob_refcnt` to count the times when a obj is refered to , it may cause problems:

```python

list1 = []
list2 = []

list1.append(list2)
list2.append(list1)

del list1
del list2

```

here , after deleting the 2 lists , `ob_refcnt` will be $(1+1 -1 = 1)>0$ , leading to memory leak

solution : **GC**

- Mark-and-Sweep
  - Mark : from `root obj`, mark all `reachable obj`
  - Sweep:`Unreachable obj`will be collected
- Generational GC
  : 'label' all the objects according to survival time . Old generation will be scanned less frequently.

## Concurrent Programming

understand the concepts of `Thread` `Process` `Parallel` `Concurrency`

note here: *concurrent* doesn't need multi-core , a simple core can take take turns operating tasks too . It is more like a *property* of a programme

use **parallel threads**  to improve efficiency

```
面试题：进程和线程的区别和联系？
进程 - 操作系统分配内存的基本单位 - 一个进程可以包含一个或多个线程
线程 - 操作系统分配CPU的基本单位
并发编程（concurrent programming）
1. 提升执行性能 - 让程序中没有因果关系的部分可以并发的执行
2. 改善用户体验 - 让耗时间的操作不会造成程序的假死
```

Learn later
