Title: List Comprehension 2
Slug: list_comprehension_2
Summary: List Comprehension 2
Date: 2016-12-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon



## First Letter Of Every Word

### Import the string module


```python
import string
```

### Create a variable that includes all punctuation and adds a blank space

string.punctuation is: !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~


```python
punct = string.punctuation + ' '
```

### Create a string for all vowels


```python
vowels = 'aeiou'
```

### Create some text


```python
phrase = 'Strictly speaking Python strings are categorized as immutable sequences'
```

### Create a variable for the first letter in every word of phase, after split up


```python
first_letter = [w[0] for w in phrase.split()]
```

### Print it out


```python
first_letter
```




    ['S', 's', 'P', 's', 'a', 'c', 'a', 'i', 's']



### In the above example here is the breakdown of the list Comprehension

- [w[0]             is the output. That is, what we want done.
- for w in          is the iterator identifier
- phrase.split()]   is the input

### You can also add a conditional statement

### Create some simulated numbers


```python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

### Create a variable called output that squared every element in numbers variable if it is divisible by 2


```python
output = [x**2 for x in numbers if x%2 == 0]
```

### View the output


```python
output
```




    [0, 4, 16, 36, 64, 100]


