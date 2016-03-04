Title: Applying Conditional Functions To List Items
Slug: applying_conditional_functions_to_list_items
Summary: Applying Conditional Functions To List Items
Date: 2016-12-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon



### Create a list of regiment names


```python
regimentNames = ['Night Riflemen', 'Jungle Scouts', 'The Dragoons', 'Midnight Revengence', 'Wily Warriors']
```

## Using A Conditional For Loop

### Create a for loop goes through the list and capitalizes an item if the first letter starts with N


```python
# create a variable for the loop results
regimentNamesCapitalized_f = []

# for every item in regimentNames
for i in regimentNames:
    # if the first letter of the regiment's name is N
    if i[0] == "N":
        # capitalize the item and add it to regimentNamesCapitalized_f
        regimentNamesCapitalized_f.append(i.upper())
    # otherwise, add it to the new list without changing anything
    else:
        regimentNamesCapitalized_f.append(i)

# View the outcome
regimentNamesCapitalized_f
```




    ['NIGHT RIFLEMEN',
     'Jungle Scouts',
     'The Dragoons',
     'Midnight Revengence',
     'Wily Warriors']



## Using List Comprehension With Conditionals

### Apply the expression x.upper to each item in the list called regiment names if it matches a condition, else apply a different function (or, in this case, do nothing)


```python
regimentNamesCapitalized_l =[x.upper() if x[0] == "N" else x for x in regimentNames]; regimentNamesCapitalized_l
```




    ['NIGHT RIFLEMEN',
     'Jungle Scouts',
     'The Dragoons',
     'Midnight Revengence',
     'Wily Warriors']



Note that the syntax for conditional list comprehension is **[x if y else z for k in v]**

- x = function if conditional statement is true
- y = conditional statement
- z = function if conditional statement is not true
- k = items in list
- v = list variable
