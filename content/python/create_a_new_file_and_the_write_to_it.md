Title: Create A New File Then Write To It  
Slug: create_a_new_file_and_the_write_to_it  
Summary: Create A New File Then Write To It Using Python.  
Date: 2017-02-02 12:00  
Category: Python  
Tags: Basics  
Authors: Chris Albon  

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

## Create A New File And Write To It


```python
# Create a file if it doesn't already exist
with open('file.txt', 'xt') as f:
    # Write to the file
    f.write('This file now exsits!')
    # Close the connection to the file
    f.close()
```

## Open The File And Read It


```python
# Open the file
with open('file.txt', 'rt') as f:
    # Read the data in the file
    data = f.read()
    # Close the connection to the file
    f.close()
```

## View The Contents Of The File


```python
# View the data in the file
data
```




    'This file now exsits!'



## Delete The File


```python
# Import the os package
import os

# Delete the file
os.remove('file.txt')
```
