Title: Generator Expressions  
Slug: generator_expressions  
Summary: Generator Expressions in Python.    
Date: 2016-01-23 12:00  
Category: Python  
Tags: Basics    
Authors: Chris Albon  

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

```python
# Create a list of students
students = ['Abe', 'Bob', 'Christina', 'Derek', 'Eleanor']
```


```python
# Create a generator expression that yields lower-case versions of the student's names
lowercase_names = (student.lower() for student in students)
```


```python
# View the generator object
lowercase_names
```




    <generator object <genexpr> at 0x104837518>




```python
# Get the next name lower-cased
next(lowercase_names)
```




    'abe'




```python
# Get the next name lower-cased
next(lowercase_names)
```




    'bob'




```python
# Get the remaining names lower-cased
list(lowercase_names)
```




    ['christina', 'derek', 'eleanor']
