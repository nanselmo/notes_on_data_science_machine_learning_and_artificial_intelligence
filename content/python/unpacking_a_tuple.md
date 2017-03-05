Title: Unpacking A Tuple  
Slug: unpacking_a_tuple  
Summary: Unpacking A Tuple in Python.    
Date: 2016-01-23 12:00  
Category: Python  
Tags: Basics    
Authors: Chris Albon  

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

## Create List Of Tuples


```python
# Create a list of tuples where the first and second element of each
# super is the first last names, respectively
soldiers = [('Steve', 'Miller'), ('Stacy', 'Markov'), ('Sonya', 'Matthews'), ('Sally', 'Mako')]
```

## Unpack Tuples


```python
# For the second element for each tuple in soldiers,
for _, last_name in soldiers:
    # print the second element
    print(last_name)
```

    Miller
    Markov
    Matthews
    Mako
