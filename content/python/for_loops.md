Title: For Loop
Slug: for_loops
Summary: For Loop
Date: 2016-05-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

The for loop iterates over each item in a sequences.


```python
# One at a time, assign each value of the sequence to i and,
for i in [432, 342, 928, 920]:
    # multiply i by 10 and store the product in a new variable, x create a new variable, x,
    x = i * 10
    # print the value of x
    print(x)
# after the entire sequence has been processes,
else:
    # print this
    print('All done!')
```

    4320
    3420
    9280
    9200
    All done!
