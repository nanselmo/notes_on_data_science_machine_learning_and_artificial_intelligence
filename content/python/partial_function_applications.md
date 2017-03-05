Title: Partial Function Applications  
Slug: partial_functions_applications  
Summary: Partial Functions Applications in Python.    
Date: 2016-01-23 12:00   
Category: Python  
Tags: Basics    
Authors: Chris Albon  

Partial function application allows us to create "functions" from other functions with pre-filled arguments. This can be very useful when we want to pipe the output of one function into a function requiring two functions.

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

## Preliminaries


```python
from functools import partial
```

## Create A Function


```python
def multiply(x, y):
    return x * y
```

## Create A Function With Y Pre-Filled


```python
double = partial(multiply, y=2)
```

## Run The Partial Function


```python
double(3)
```




    6
