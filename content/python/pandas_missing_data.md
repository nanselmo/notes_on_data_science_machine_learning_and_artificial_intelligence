Title: Missing Data In Pandas Dataframe
Slug: pandas_missing_data
Summary: Missing Data In Pandas Dataframe
Date: 2016-12-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon



### import modules


```python
import pandas as pd
import numpy as np
```

### Create dataframe with missing values


```python
raw_data = {'first_name': ['Jason', np.nan, 'Tina', 'Jake', 'Amy'], 
        'last_name': ['Miller', np.nan, 'Ali', 'Milner', 'Cooze'], 
        'age': [42, np.nan, 36, 24, 73], 
        'sex': ['m', np.nan, 'f', 'm', 'f'], 
        'preTestScore': [4, np.nan, np.nan, 2, 3],
        'postTestScore': [25, np.nan, np.nan, 62, 70]}
df = pd.DataFrame(raw_data, columns = ['first_name', 'last_name', 'age', 'sex', 'preTestScore', 'postTestScore'])
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
      <th>sex</th>
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
      <td>   m</td>
      <td>  4</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>1</th>
      <td>   NaN</td>
      <td>    NaN</td>
      <td>NaN</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>  Tina</td>
      <td>    Ali</td>
      <td> 36</td>
      <td>   f</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td>   m</td>
      <td>  2</td>
      <td> 62</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td>   f</td>
      <td>  3</td>
      <td> 70</td>
    </tr>
  </tbody>
</table>
</div>



### Drop missing observations


```python
df_no_missing = df.dropna()
df_no_missing
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>first_name</th>
      <th>last_name</th>
      <th>age</th>
      <th>sex</th>
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
      <td> m</td>
      <td> 4</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td> m</td>
      <td> 2</td>
      <td> 62</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td> f</td>
      <td> 3</td>
      <td> 70</td>
    </tr>
  </tbody>
</table>
</div>



### Drop rows where all cells in that row is NA


```python
df_cleaned = df.dropna(how='all')
df_cleaned
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>first_name</th>
      <th>last_name</th>
      <th>age</th>
      <th>sex</th>
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
      <td> m</td>
      <td>  4</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>2</th>
      <td>  Tina</td>
      <td>    Ali</td>
      <td> 36</td>
      <td> f</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td> m</td>
      <td>  2</td>
      <td> 62</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td> f</td>
      <td>  3</td>
      <td> 70</td>
    </tr>
  </tbody>
</table>
</div>



### Create a new column full of missing values


```python
df['location'] = [np.nan, np.nan, np.nan, np.nan, np.nan]
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
      <th>sex</th>
      <th>preTestScore</th>
      <th>postTestScore</th>
      <th>location</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td> Jason</td>
      <td> Miller</td>
      <td> 42</td>
      <td>   m</td>
      <td>  4</td>
      <td> 25</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>   NaN</td>
      <td>    NaN</td>
      <td>NaN</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>  Tina</td>
      <td>    Ali</td>
      <td> 36</td>
      <td>   f</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td>   m</td>
      <td>  2</td>
      <td> 62</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td>   f</td>
      <td>  3</td>
      <td> 70</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



### Drop column if they only contain missing values


```python
df.dropna(axis=1, how='all')
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>first_name</th>
      <th>last_name</th>
      <th>age</th>
      <th>sex</th>
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
      <td>   m</td>
      <td>  4</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>1</th>
      <td>   NaN</td>
      <td>    NaN</td>
      <td>NaN</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>  Tina</td>
      <td>    Ali</td>
      <td> 36</td>
      <td>   f</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td>   m</td>
      <td>  2</td>
      <td> 62</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td>   f</td>
      <td>  3</td>
      <td> 70</td>
    </tr>
  </tbody>
</table>
</div>



### Drop rows that contain less than five observations

This is really mostly useful for time series


```python
df.dropna(thresh=5)
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>first_name</th>
      <th>last_name</th>
      <th>age</th>
      <th>sex</th>
      <th>preTestScore</th>
      <th>postTestScore</th>
      <th>location</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td> Jason</td>
      <td> Miller</td>
      <td> 42</td>
      <td> m</td>
      <td> 4</td>
      <td> 25</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td> m</td>
      <td> 2</td>
      <td> 62</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td> f</td>
      <td> 3</td>
      <td> 70</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



### Fill in missing data with zeros


```python
df.fillna(0)
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>first_name</th>
      <th>last_name</th>
      <th>age</th>
      <th>sex</th>
      <th>preTestScore</th>
      <th>postTestScore</th>
      <th>location</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td> Jason</td>
      <td> Miller</td>
      <td> 42</td>
      <td> m</td>
      <td> 4</td>
      <td> 25</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>     0</td>
      <td>      0</td>
      <td>  0</td>
      <td> 0</td>
      <td> 0</td>
      <td>  0</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>  Tina</td>
      <td>    Ali</td>
      <td> 36</td>
      <td> f</td>
      <td> 0</td>
      <td>  0</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td> m</td>
      <td> 2</td>
      <td> 62</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td> f</td>
      <td> 3</td>
      <td> 70</td>
      <td> 0</td>
    </tr>
  </tbody>
</table>
</div>



### Fill in missing in preTestScore with the mean value of preTestScore

inplace=True means that the changes are saved to the df right away


```python
df["preTestScore"].fillna(df["preTestScore"].mean(), inplace=True)
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
      <th>sex</th>
      <th>preTestScore</th>
      <th>postTestScore</th>
      <th>location</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td> Jason</td>
      <td> Miller</td>
      <td> 42</td>
      <td>   m</td>
      <td> 4</td>
      <td> 25</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>   NaN</td>
      <td>    NaN</td>
      <td>NaN</td>
      <td> NaN</td>
      <td> 3</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>  Tina</td>
      <td>    Ali</td>
      <td> 36</td>
      <td>   f</td>
      <td> 3</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td>   m</td>
      <td> 2</td>
      <td> 62</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td>   f</td>
      <td> 3</td>
      <td> 70</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



### Fill in missing in postTestScore with each sex's mean value of postTestScore


```python
df["postTestScore"].fillna(df.groupby("sex")["postTestScore"].transform("mean"), inplace=True)
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
      <th>sex</th>
      <th>preTestScore</th>
      <th>postTestScore</th>
      <th>location</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td> Jason</td>
      <td> Miller</td>
      <td> 42</td>
      <td>   m</td>
      <td> 4</td>
      <td> 25</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>   NaN</td>
      <td>    NaN</td>
      <td>NaN</td>
      <td> NaN</td>
      <td> 3</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>  Tina</td>
      <td>    Ali</td>
      <td> 36</td>
      <td>   f</td>
      <td> 3</td>
      <td> 70</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td>   m</td>
      <td> 2</td>
      <td> 62</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td>   f</td>
      <td> 3</td>
      <td> 70</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



### Select some raws but ignore the missing data points


```python
# Select the rows of df where age is not NaN and sex is not NaN
df[df['age'].notnull() & df['sex'].notnull()]
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>first_name</th>
      <th>last_name</th>
      <th>age</th>
      <th>sex</th>
      <th>preTestScore</th>
      <th>postTestScore</th>
      <th>location</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td> Jason</td>
      <td> Miller</td>
      <td> 42</td>
      <td> m</td>
      <td> 4</td>
      <td> 25</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>  Tina</td>
      <td>    Ali</td>
      <td> 36</td>
      <td> f</td>
      <td> 3</td>
      <td> 70</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Jake</td>
      <td> Milner</td>
      <td> 24</td>
      <td> m</td>
      <td> 2</td>
      <td> 62</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>   Amy</td>
      <td>  Cooze</td>
      <td> 73</td>
      <td> f</td>
      <td> 3</td>
      <td> 70</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>


