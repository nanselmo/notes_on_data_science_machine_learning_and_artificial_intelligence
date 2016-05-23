Title: Iterating Through The Rows Of Multiple Columns In Pandas
Slug: pandas_iterate_over_rows_of_multiple_columns
Summary: Iterating Through The Rows Of Multiple Columns In Pandas
Date: 2016-05-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon


```python
# Import modules
import pandas as pd
import numpy as np
```


```python
raw_data = {'first_name': ['Jason', 'Jason', 'Tina', 'Jake', 'Amy'],
        'last_name': ['Miller', 'Miller', 'Ali', 'Milner', 'Cooze'],
        'age': [42, 42, 36, 24, 73],
        'preTestScore': [4, 4, 31, 2, 3],
        'postTestScore': [25, 25, 57, 62, 70]}
df = pd.DataFrame(raw_data, columns = ['first_name', 'last_name', 'age', 'preTestScore', 'postTestScore'])
df
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>first_name</th>
      <th>last_name</th>
      <th>age</th>
      <th>preTestScore</th>
      <th>postTestScore</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td> Jason</td>
      <td> Miller</td>
      <td> 42</td>
      <td>  4</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>1</th>
      <td> Jason</td>
      <td> Miller</td>
      <td> 42</td>
      <td>  4</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>2</th>
      <td>  Tina</td>
      <td>    Ali</td>
      <td> 36</td>
      <td> 31</td>
      <td> 57</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td>  2</td>
      <td> 62</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td>  3</td>
      <td> 70</td>
    </tr>
  </tbody>
</table>
</div>



## Iterate Over The Rows Of Two Columns


```python
# Create an empty column for the full names
df['full_name'] = np.NaN

# Create an iteration counter
i = 0

# For each element in first_name and last_name,
for first, last in zip(df['first_name'], df['last_name']):
    # Change the value of the i'th row in full_name
    # to the combination of the first and last name
    df['full_name'][i] = first + ' ' + last

    # Add one to the iteration counter
    i = i+1
```


```python
# View the dataframe
df
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>first_name</th>
      <th>last_name</th>
      <th>age</th>
      <th>preTestScore</th>
      <th>postTestScore</th>
      <th>full_name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td> Jason</td>
      <td> Miller</td>
      <td> 42</td>
      <td>  4</td>
      <td> 25</td>
      <td> Jason Miller</td>
    </tr>
    <tr>
      <th>1</th>
      <td> Jason</td>
      <td> Miller</td>
      <td> 42</td>
      <td>  4</td>
      <td> 25</td>
      <td> Jason Miller</td>
    </tr>
    <tr>
      <th>2</th>
      <td>  Tina</td>
      <td>    Ali</td>
      <td> 36</td>
      <td> 31</td>
      <td> 57</td>
      <td>     Tina Ali</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td>  2</td>
      <td> 62</td>
      <td>  Jake Milner</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td>  3</td>
      <td> 70</td>
      <td>    Amy Cooze</td>
    </tr>
  </tbody>
</table>
</div>
