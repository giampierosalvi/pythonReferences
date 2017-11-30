
# Example on how python uses references
The example below shows that python uses references every time you assing an object to a new variable. Even if you reshape an array, the data contained in the original and reshaped version is stored only once. Changing the values in the original array, will change the reshaped array as well. The same is true for other matrix operations, such as the transpose, for example. If you want to create a new object, you have to do this explicitely (case d).


```python
import numpy as np
# create a simple array
a = np.array([1, 2, 3, 4])
# show a
a
```




    array([1, 2, 3, 4])




```python
# reshape array into two dimensions
# exaclty the same as np.reshape(a, (2,2))
b = a.reshape((2,2))
# show b
b
```




    array([[1, 2],
           [3, 4]])




```python
# transpose b
c = b.T
# show c
c
```




    array([[1, 3],
           [2, 4]])




```python
# make explicit copy while reshaping
d = np.array(a).reshape((2,2))
# show d
d
```




    array([[1, 2],
           [3, 4]])




```python
# change one element in a
a[1] = 1234
# show a (changed)
a
```




    array([   1, 1234,    3,    4])




```python
# show b (changed)
b
```




    array([[   1, 1234],
           [   3,    4]])




```python
# show c (changed)
c
```




    array([[   1,    3],
           [1234,    4]])




```python
# show d (unchanged)
d
```




    array([[1, 2],
           [3, 4]])


