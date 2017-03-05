Title: Enumerate A List
Slug: enumerate_a_list
Summary: Enumerate A List
Date: 2016-05-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

```python
# Create a list of strings
data = ['One','Two','Three','Four','Five']
```


```python
# For each item in the enumerated variable, data
for item in enumerate(data):
    # Print the whole enumerated element
    print(item)
    # Print only the value (not the index number)
    print(item[1])
```

    (0, 'One')
    One
    (1, 'Two')
    Two
    (2, 'Three')
    Three
    (3, 'Four')
    Four
    (4, 'Five')
    Five
