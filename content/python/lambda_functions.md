Title: Lambda Functions
Slug: lambda_functions
Summary: Lambda Functions
Date: 2016-05-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon



Lambda functions can ask as mini-functions, allowing you to create small bits of code into things like series.

### Create a series, called pipeline, that contains three mini functions


```python
pipeline = [lambda x: x **2 - 1 + 5,
            lambda x: x **20 - 2 + 3,
            lambda x: x **200 - 1 + 4]
```

### For each item in pipeline, run the lambda function with x = 3


```python
for f in pipeline:
    print(f(3))
```
