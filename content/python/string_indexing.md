Title: String Indexing
Slug: string_indexing
Summary: String Indexing
Date: 2016-05-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

### Create a string


```python
string = 'Strings are defined as ordered collections of characters.'
```

### Print the entire string


```python
string[:]
```




    'Strings are defined as ordered collections of characters.'



### Print the first three characters


```python
string[0:2]
```




    'St'



### Print the first three characters


```python
string[:2]
```




    'St'



### Print the last three characters


```python
string[-3:]
```




    'rs.'



### Print the third to fifth character


```python
string[2:4]
```




    'ri'



### Print the first to the tenth character, skipping every other character


```python
string[0:9:2]
```




    'Srnsa'



### Print the string in reverse


```python
string[::-1]
```




    '.sretcarahc fo snoitcelloc deredro sa denifed era sgnirtS'
