Title: List Comprehension 1
Slug: list_comprehension
Summary: List Comprehension 1
Date: 2016-05-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon



### Create a matrix using lists


```python
matrix = [[1, 2, 3],
          [4, 5, 6],
          [7, 8, 9]]
```

### View the matrix


```python
matrix
```




    [[1, 2, 3], [4, 5, 6], [7, 8, 9]]



### View the items in column 2

"build a new list by running an expression on each item in a sequence, one at a time, from left to right." - Learning Python

### Create a variable called col2 that takes the second item from each row (i.e. nested list) in the list matrix


```python
col2 = [row[1] for row in matrix]
```

### View the column


```python
col2
```




    [2, 5, 8]



### Grab the diag


```python
diag = [matrix[i][i] for i in [0, 1, 2]]
```

### Print it


```python
diag
```




    [1, 5, 9]


