# Machine Learning

## KNN(k nearest neighbor)

**Simple**
 thought use a dictionary to map history data . However new data may have no same key stored in the dict , so we find k nearest neighbor and calculate the mean value of them

```python
import heapq
#heap queue , orders a function to get k smallest data
import statistics

def predict_knn(history_data , param_in , k = 5):
    heighbors = heapq.nsmallest(k,history_data,key = lambda x: (x-param_in)**2)
    return statistic.mean([history_data[neighbor] for neighbor in neighbors])
```

More about distance :  

- Minkowski Distance : $d(x,y) = (\sum_{i=i}^n |x_i-y_i|^p)^\frac{1}{p}$

- Manhattan Distance : p = 1
- Euclid Distance    : p = 2
- Chebyshev Distance : $p\to \infty$

