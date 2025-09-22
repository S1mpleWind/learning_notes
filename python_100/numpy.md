# Learn Numpy module

Learn the numpy module to prepare a bit for pytorch

## ndarray

`ndarray` stands for *N-dimensional array* , is the core data type of Numpy

### 1.initialization

- use `array` function to pass a list to initialize

```python
array1 = numpy.array([1,2,3,4,5])
```

- use `arange(start,end,step)`

```python
array2 = numpy.arange(0,20,2)
```

- use `linspace(start,end,numbers)`

```python
array3=numpy.linspace(-1,1,11)
```

- use `logspace(start_log,end_log,num,base)`

- use `fromstring( string , sep=,dtype=)

```python
array6 = numpy.fromstring('1,2,3,4,5' , sep = ',' , dtype = 'i8')
```

- use *iterator/generator* by calling `fromiter` function

- use special functions like `zeros` , `ones` , `full`
- use `imread` to extract *RGB* data from a image

---

### 2.Properties

- `size` : number of elements
- `shape`:
- `dtype`: datatype ( i8=int64 , i1 = int8 , f4 = float32)
- `ndim` : dimension
- `itemsize`
- `nbytes` : total bytes

---

### 3.Index operation

like lists in python , `narray` have **index operation and slice** too

When calling slice operation , between `[]` we can use `,` to add more **dimensions**  
eg.`a[2, 1:2 , 1] = a [2] + [1,2] + [1]` applying to each dimension

fancy/advanced indexing : use a list or of **nums** or **bool** to select elements

we can use `imread` + *slice* to accomplish reverting a picture

---

### 4. other functions 

`reshape(row,col)`: if row/col = **-1** , it means that the number will be **auto-judged** , eg `reshape(-1,1)` will reshape to a single column


---

### get statistic info

- `.sum`
- `.mean`
- `.median`
- `.quantile(percent)`
- `max`
- `min`
- `var` : variance
- `std` : standard deviation

learn more when needed ......

---
---

## Operation of array(matrix)

All the operating functions will be called on every members in the array . Beside *arithmetic operations* , *boolen operations* can also be applied .

The operation between two arrays is also legal as long as they have the same **shape**

We can also call *universal unary funciton* in `numpy`

- `abs/fabs`
- `sqrt`
- `square`
- `exp`
- `log/log10...`
- `sign`
- `ceil/floor` : ceil/floor the nums to an integer
- `isnan` : if is `NaN` , return `True`
- `isfinite/isinf`
- `cos/sin/tan/arcsin...`
- `rint/round`

Of course there are *Universal Binary Function* too

- `add/subtract(x,y)`
- `multiply/divide(x,y)`
- `dot`
- `inner` : dot product is a special case of inner product in Euclid Space
- `outer`
- etc

**Broadcast mechanism** : when 2 arrays have different shapes , the array that has the dimension reduced shape of the other one will be *broadcast*ed to a higher-dimension array.

Other popular functions include :

- `copy`:
- `unique`: return an array that has no repeated value
- `sort` : return a copy of sorted array
- `stack/hstack/vstack`:
- `split/hsplit/vsplit`
- `flip`
- etc

Call `dot` and `cross` to operate *dot product* and *cross product*

---

## Matrix

Matrix is a module specially designed for linear algebra operation.

### property

- `A`:return corresponding `ndarray`
- `A1`
- `I`: M^(-1)
- `T`:
- `shape`
- `size`

### Function

- `diag`
- `det`
- `trace`
- etc

---
---

## Polynomial

use module `numpy.polynomial`

`deriv()`,`integ()`: calculate derivation and integal

`fit(x,y,deg=n)` to fit a polynomial