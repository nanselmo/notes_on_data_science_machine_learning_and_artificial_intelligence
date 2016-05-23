Title: Finding A Trend Line Of Data
Slug: scipy_fitting_trendline
Summary: Finding A Trend Line Of Data
Date: 2016-05-01 12:00
Category: Python
Tags: Other
Authors: Chris Albon



**Note:** Based on: SciPy And NumPy

### Import modules


```python
import numpy as np
from scipy.optimize import curve_fit
```

### Creating some clean data


```python
# create a function called func(),
def func(x, a, b):
    # that multiplies a and x, then adds b
    return a * x + b
```


```python
# create 100 elements, evenly spaced between 0 and 10
x = np.linspace(0, 10, 100)

# mix up the data by applying func()
y = func(x, 1, 2)

# view the first few entries
y[0:10]
```




    array([ 2.        ,  2.1010101 ,  2.2020202 ,  2.3030303 ,  2.4040404 ,
            2.50505051,  2.60606061,  2.70707071,  2.80808081,  2.90909091])



### Add noise to the data


```python
# Add some randomness to the data by multiplying y by 100 values drawn from the normal distribution
yn = y + 0.9 * np.random.normal(size=len(x))

# view the first few entries
yn[0:10]
```




    array([ 3.63606696,  3.51496281,  2.68882029,  2.11995938,  2.36446115,
            3.41454019,  1.66117548,  2.59706936,  3.22359943,  2.16499171])



### Fitting a line to the data

- func = the model function
- x = the independent variable
- y = the dependent variable


```python
# return an array of values (popt) so that the squared error of the line is minimized
# also return a 2d array with eh covariance of popt
popt, pcov = curve_fit(func, x, yn)
```

### What is popt?

popt returns the values of x (the independent variable) and yn (the dependent variable) with the smallest squared error


```python
popt
```




    array([ 0.92825153,  2.25863607])



This means that if x = 0.92 and y = 2.25, the function (called func()) best fits the data
