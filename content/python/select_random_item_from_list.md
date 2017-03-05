Title: Select Random Item From A Lists
Slug: select_random_item_from_list  
Summary: Select Random Item From A Lists in Python.
Date: 2016-01-23 12:00  
Category: Python  
Tags: Basics    
Authors: Chris Albon  

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

## Preliminaries


```python
from random import choice
```

## Create List


```python
# Make a list of crew members
crew_members = ['Steve', 'Stacy', 'Miller', 'Chris', 'Bill', 'Jack']
```

## Select Random Item From List


```python
# Choose a random crew member
choice(crew_members)
```




    'Stacy'
