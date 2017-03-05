Title: Iterate Over Multiple Lists Simultaneously  
Slug: iterate_over_multiple_lists_simultaneously  
Summary: Iterate Over Multiple Lists Simultaneously Using Python.  
Date: 2017-02-02 12:00  
Category: Python  
Tags: Basics  
Authors: Chris Albon  

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

## Create Two Lists


```python
names = ['James', 'Bob', 'Sarah', 'Marco', 'Nancy', 'Sally']
ages = [42, 13, 14, 25, 63, 23]
```

## Iterate Over Both Lists At Once


```python
for name, age in zip(names, ages):
     print(name, age)
```

    James 42
    Bob 13
    Sarah 14
    Marco 25
    Nancy 63
    Sally 23
