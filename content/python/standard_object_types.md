Title: Built-In Object Types
Slug: standard_object_types
Summary: Built-In Object Types
Date: 2016-05-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon



## Numbers

### Create a variable


```python
x = 493
```

### View the variable x


```python
x
```




    493



## Strings

### Create a single


```python
warning = "There is an earthquake in the Pacific."
```

### View the object "warning


```python
warning
```




    'There is an earthquake in the Pacific.'



### View the first letter of the "warning" string variable.


```python
warning[0]
```




    'T'



### View the last letter of the "warning" string variable


```python
warning[-1]
```




    '.'



### View the number of characters in the "warning" string variable


```python
len(warning)
```




    38



## Lists

### Create a list of strings


```python
employees = ["Jake", "Steve", "Sarah"]
```

### View the first element the list


```python
employees[0]
```




    'Jake'



### Add two new employees to the list.


```python
employees = employees + ["Bill", "Stan"]
```

### View the entire new list of employees.


```python
employees
```




    ['Jake', 'Steve', 'Sarah', 'Bill', 'Stan']



## Dictionaries

### Create a dictionary of greetings


```python
greetings = {
	'English': 'Hello',
	'Spanish': 'Hola'
}
```

### View the greetings dictionary


```python
greetings
```




    {'English': 'Hello', 'Spanish': 'Hola'}



## Tuples

### Create a toople


```python
dates = (12, 15, 92)
```

## Files

### Open a new file in output mode.


```python
f = open('data.txt')
```


    ---------------------------------------------------------------------------
    FileNotFoundError                         Traceback (most recent call last)

    <ipython-input-58-eff2ebdcabd0> in <module>()
    ----> 1 f = open('data.txt')
    

    FileNotFoundError: [Errno 2] No such file or directory: 'data.txt'


### Close out the file connection.


```python
f.close()
```


    ---------------------------------------------------------------------------
    NameError                                 Traceback (most recent call last)

    <ipython-input-59-fa01cc0d8510> in <module>()
    ----> 1 f.close()
    

    NameError: name 'f' is not defined


### Find Out An Object's Type


```python
type(dates)
```




    tuple


