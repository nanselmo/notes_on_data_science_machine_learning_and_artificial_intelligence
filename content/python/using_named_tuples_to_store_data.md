Title: Using Named Tuples To Store Data  
Slug: using_named_tuples_to_store_data  
Summary: Using Named Tuples To Store Data in Python.    
Date: 2016-01-23 12:00  
Category: Python  
Tags: Basics    
Authors: Chris Albon  

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

## Preliminaries


```python
from collections import namedtuple
```

## Create A Named Tuple


```python
Vehicle = namedtuple('Vehicle', 'make model wheels manual')
```

## Create An Entry


```python
forrester = Vehicle('Forrester', 'Subaru', 4, True)
```

## View The Data In Entry


```python
forrester.model
```




    'Subaru'




```python
forrester.wheels
```




    4
