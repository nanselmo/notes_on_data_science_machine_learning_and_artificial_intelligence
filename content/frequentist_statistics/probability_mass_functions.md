Title: Probability Mass Functions  
Slug: probability_mass_functions  
Summary: Probability Mass Functions in Python.    
Date: 2016-02-08 12:00  
Category: Frequentist Statistics  
Tags: Basics
Authors: Chris Albon  

## Create Data


```python
data = [3,2,3,4,2,3,5,2,2,33,3,5,2,2,5,6,62,2,2,3,6,6,2,23,3,2,3]
```

## Create A Count Of Values


```python
# Create a dictionary to store the counts
count = {}

# For each value in the data
for observation in data:

    # An a key, value pair, with the observation being the key
    # and the value being +1
    count[observation] = count.get(observation, 0) + 1
```

## Normalize The Count To Between 0 and 1


```python
# Calculate the number of observations
n = len(data)

# Create a dictionary
probability_mass_function = {}

# For each unique value,
for unique_value, count in count.items():
    # Normalize the count by dividing by the length of data, add to the PMC dictionary
    probability_mass_function[unique_value] = count / n
```


```python
probability_mass_function
```




    {2: 0.37037037037037035,
     3: 0.25925925925925924,
     4: 0.037037037037037035,
     5: 0.1111111111111111,
     6: 0.1111111111111111,
     23: 0.037037037037037035,
     33: 0.037037037037037035,
     62: 0.037037037037037035}
