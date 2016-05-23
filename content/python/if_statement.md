Title: if Statement
Slug: if_statement
Summary: if Statement
Date: 2016-05-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon



### Import the random module.


```python
import random
```

### Create a variable of the true number of deaths of an event.


```python
deaths = 6
```

### Create a variable that randomly create a integer between 0 and 10.


```python
guess = random.randint(0,10)
```

### if guess equals deaths


```python
if guess == deaths:
    # then print this
    print('Correct!')
# else if guess is lower than deaths
elif guess < deaths:
    # then print this
    print('No, it is higher.')
# if guess is none of the above
else:
    # print this
    print('No, it is lower')
```

    Correct!

