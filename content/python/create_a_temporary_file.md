Title: Create A Temporary File  
Slug: create_a_temporary_file  
Summary: Create A Temporary File Using Python.  
Date: 2017-02-02 12:00  
Category: Python  
Tags: Basics  
Authors: Chris Albon  

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

## Preliminaries


```python
from tempfile import NamedTemporaryFile
```

## Create A Temporary File


```python
f = NamedTemporaryFile('w+t')
```

## Write To The Temp File


```python
# Write to the file, the output is the number of characters
f.write('Nobody lived on Deadweather but us and the pirates. It wasn’t hard to understand why.')
```




    85



## View The Tmp File's Name


```python
f.name
```




    '/var/folders/0b/pj3wsd750fjf8xzfb0n127w80000gn/T/tmphv1dkovx'



## Read The File


```python
# Go to the top of the file
f.seek(0)

# Read the file
f.read()
```




    'Nobody lived on Deadweather but us and the pirates. It wasn’t hard to understand why.'



## Close (And Thus Delete) The File


```python
f.close()
```
