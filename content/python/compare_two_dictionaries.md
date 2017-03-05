Title: Compare Two Dictionaries  
Slug: compare_two_dictionaries  
Summary: Compare Two Dictionaries Using Python.  
Date: 2017-02-02 12:00  
Category: Python  
Tags: Basics  
Authors: Chris Albon  

One of the great features of Python dictionaries is that they are hashtables, meaning we can do some operations at O(1) time-complexity.

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

## Make Two Dictionaries


```python
importers = {'El Salvador' : 1234,
             'Nicaragua' : 152,
             'Spain' : 252
            }

exporters = {'Spain' : 252,
             'Germany' : 251,
             'Italy' : 1563
             }
```

## Find Duplicate Keys


```python
# Find the intersection of importers and exporters
importers.keys() & exporters.keys()
```




    {'Spain'}



## Find Difference In Keys


```python
# Find the difference between importers and exporters
importers.keys() - exporters.keys()
```




    {'El Salvador', 'Nicaragua'}



## Find Key, Values Pairs In Common


```python
# Find countries where the amount of exports matches the amount of imports
importers.items() & exporters.items()
```




    {('Spain', 252)}
