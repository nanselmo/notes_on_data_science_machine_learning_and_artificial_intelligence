Title: Rename Multiple Pandas Dataframe Column Names At Once
Slug: pandas_rename_multiple_columns
Summary: Rename Multiple Pandas Dataframe Column Names At Once
Date: 2016-12-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon



## Preliminaries


```
# Import modules
import pandas as pd

# Set ipython's max row display
pd.set_option('display.max_row', 1000)

# Set iPython's max column width to 50
pd.set_option('display.max_columns', 50)
```

## Create an example dataframe


```
# Create an example dataframe
data = {'Commander': ['Jason', 'Molly', 'Tina', 'Jake', 'Amy'], 
        'Date': ['2012, 02, 08', '2012, 02, 08', '2012, 02, 08', '2012, 02, 08', '2012, 02, 08'], 
        'Score': [4, 24, 31, 2, 3]}
df = pd.DataFrame(data, index = ['Cochice', 'Pima', 'Santa Cruz', 'Maricopa', 'Yuma'])
df
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Commander</th>
      <th>Date</th>
      <th>Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Cochice</th>
      <td> Jason</td>
      <td> 2012, 02, 08</td>
      <td>  4</td>
    </tr>
    <tr>
      <th>Pima</th>
      <td> Molly</td>
      <td> 2012, 02, 08</td>
      <td> 24</td>
    </tr>
    <tr>
      <th>Santa Cruz</th>
      <td>  Tina</td>
      <td> 2012, 02, 08</td>
      <td> 31</td>
    </tr>
    <tr>
      <th>Maricopa</th>
      <td>  Jake</td>
      <td> 2012, 02, 08</td>
      <td>  2</td>
    </tr>
    <tr>
      <th>Yuma</th>
      <td>   Amy</td>
      <td> 2012, 02, 08</td>
      <td>  3</td>
    </tr>
  </tbody>
</table>
</div>



## Rename Column Names


```
df.columns = ['Leader', 'Time', 'Score']
```


```
df
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Leader</th>
      <th>Time</th>
      <th>Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Cochice</th>
      <td> Jason</td>
      <td> 2012, 02, 08</td>
      <td>  4</td>
    </tr>
    <tr>
      <th>Pima</th>
      <td> Molly</td>
      <td> 2012, 02, 08</td>
      <td> 24</td>
    </tr>
    <tr>
      <th>Santa Cruz</th>
      <td>  Tina</td>
      <td> 2012, 02, 08</td>
      <td> 31</td>
    </tr>
    <tr>
      <th>Maricopa</th>
      <td>  Jake</td>
      <td> 2012, 02, 08</td>
      <td>  2</td>
    </tr>
    <tr>
      <th>Yuma</th>
      <td>   Amy</td>
      <td> 2012, 02, 08</td>
      <td>  3</td>
    </tr>
  </tbody>
</table>
</div>




```
df.rename(columns={'Leader': 'Commander'}, inplace=True)
```


```
df
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Commander</th>
      <th>Time</th>
      <th>Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Cochice</th>
      <td> Jason</td>
      <td> 2012, 02, 08</td>
      <td>  4</td>
    </tr>
    <tr>
      <th>Pima</th>
      <td> Molly</td>
      <td> 2012, 02, 08</td>
      <td> 24</td>
    </tr>
    <tr>
      <th>Santa Cruz</th>
      <td>  Tina</td>
      <td> 2012, 02, 08</td>
      <td> 31</td>
    </tr>
    <tr>
      <th>Maricopa</th>
      <td>  Jake</td>
      <td> 2012, 02, 08</td>
      <td>  2</td>
    </tr>
    <tr>
      <th>Yuma</th>
      <td>   Amy</td>
      <td> 2012, 02, 08</td>
      <td>  3</td>
    </tr>
  </tbody>
</table>
</div>


