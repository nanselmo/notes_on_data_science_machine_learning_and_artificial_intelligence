Title: Function Annotation Examples  
Slug: function_annotations_examples  
Summary: Function Annotation Examples in Python.      
Date: 2016-01-23 12:00     
Category: Python    
Tags: Basics    
Authors: Chris Albon

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK). 

Interesting in learning more? Check out [Fluent Python](http://amzn.to/2jYU506)

## Create A Function With Annotations


```python
'''
Create a function.

The argument 'text' is the string to print with the default value 'default string'
and the argument

The argument 'n' is an integer of times to print with the default value of 1.

The function should return a string.
'''
def print_text(text:'string to print'='default string', n:'integer, times to print'=1) -> str:
    return text * n
```

## Run The Function


```python
# Run the function with arguments
print_text('string', 4)
```




    'stringstringstringstring'




```python
# Run the function with default arguments
print_text()
```




    'default string'
