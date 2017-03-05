Title: Swapping variable values
Slug: swapping_variable_values
Summary: Swapping variable values
Date: 2016-05-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

### Setup the originally variables and their values


```python
one = 1
two = 2
```

### View the original variables


```python
'one =', one, 'two =', two
```




    ('one =', 1, 'two =', 2)



### Swap the values


```python
one, two = two, one
```

### View the swapped values, notice how the values for each variable have changed


```python
'one =', one, 'two =', two
```




    ('one =', 2, 'two =', 1)
