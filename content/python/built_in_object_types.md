Title: Built-In Object Types
Slug: built_in_object_types
Summary: Built-In Object Types
Date: 2016-05-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon



## Numbers


```python
# Add two numbers togther
x = 493
```


```python
# View the object x
x
```




    493



## Strings


```python
# Create a string
warning = "There is an earthquake in the Pacific."
```


```python
# View the object "warning"
warning
```




    'There is an earthquake in the Pacific.'




```python
# View the first letter of the "warning" string variable
warning[0]
```




    'T'




```python
# View the last letter of the "warning" string variable
warning[-1]
```




    '.'




```python
# View the number of characters in the "warning" string variable
len(warning)
```




    38



## Lists


```python
# Create a list of strings
employees = ["Jake", "Steve", "Sarah"]
```


```python
# View the first element the list
employees[0]
```




    'Jake'




```python
# Add two new employees to the list
employees = employees + ["Bill", "Stan"]
```


```python
# View the entire new list of employees
employees
```




    ['Jake', 'Steve', 'Sarah', 'Bill', 'Stan']



## Dictionaries


```python
# Create a dictionary of greetings
greetings = {
   'English': 'Hello',
   'Spanish': 'Hola'
}
```


```python
# View the greetings dictionary
greetings
```




    {'English': 'Hello', 'Spanish': 'Hola'}



## Tuples


```python
# Create a tuple
dates = (12, 15, 92)
```

## Files


```python
# Open a new file in output mode.
# f = open('data.txt')
```


```python
# Close out the file connection
# f.close()
```


```python
# Find Out An Object's Type
# type(dates)
```
