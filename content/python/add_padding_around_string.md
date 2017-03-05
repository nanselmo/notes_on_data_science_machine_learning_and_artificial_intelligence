Title: Add Padding Around String  
Slug: add_padding_around_string  
Summary: Add Padding Around String Using Python.  
Date: 2017-02-02 12:00  
Category: Python  
Tags: Basics  
Authors: Chris Albon  

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

## Create Some Text


```python
text = 'Chapter 1'
```

## Add Padding Around Text


```python
# Add Spaces Of Padding To The Left
format(text, '>20')
```




    '           Chapter 1'




```python
# Add Spaces Of Padding To The Right
format(text, '<20')
```




    'Chapter 1           '




```python
# Add Spaces Of Padding On Each Side
format(text, '^20')
```




    '     Chapter 1      '




```python
# Add * Of Padding On Each Side
format(text, '*^20')
```




    '*****Chapter 1******'
