Title: Sorting Rows Of pandas Dataframes
Slug: pandas_sorting_rows_dataframe
Summary: Sorting Rows Of pandas Dataframes
Date: 2016-12-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon



### import modules


```python
import pandas as pd
```

### Create dataframe


```python
data = {'name': ['Jason', 'Molly', 'Tina', 'Jake', 'Amy'], 
        'year': [2012, 2012, 2013, 2014, 2014], 
        'reports': [4, 24, 31, 2, 3],
        'coverage': [25, 94, 57, 62, 70]}
df = pd.DataFrame(data, index = ['Cochice', 'Pima', 'Santa Cruz', 'Maricopa', 'Yuma'])
df
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>coverage</th>
      <th>name</th>
      <th>reports</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Cochice</th>
      <td> 25</td>
      <td> Jason</td>
      <td>  4</td>
      <td> 2012</td>
    </tr>
    <tr>
      <th>Pima</th>
      <td> 94</td>
      <td> Molly</td>
      <td> 24</td>
      <td> 2012</td>
    </tr>
    <tr>
      <th>Santa Cruz</th>
      <td> 57</td>
      <td>  Tina</td>
      <td> 31</td>
      <td> 2013</td>
    </tr>
    <tr>
      <th>Maricopa</th>
      <td> 62</td>
      <td>  Jake</td>
      <td>  2</td>
      <td> 2014</td>
    </tr>
    <tr>
      <th>Yuma</th>
      <td> 70</td>
      <td>   Amy</td>
      <td>  3</td>
      <td> 2014</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 4 columns</p>
</div>



### Sort the dataframe's rows by reports, in descending order


```python
df.sort_index(by='reports', ascending=0)
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>coverage</th>
      <th>name</th>
      <th>reports</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Santa Cruz</th>
      <td> 57</td>
      <td>  Tina</td>
      <td> 31</td>
      <td> 2013</td>
    </tr>
    <tr>
      <th>Pima</th>
      <td> 94</td>
      <td> Molly</td>
      <td> 24</td>
      <td> 2012</td>
    </tr>
    <tr>
      <th>Cochice</th>
      <td> 25</td>
      <td> Jason</td>
      <td>  4</td>
      <td> 2012</td>
    </tr>
    <tr>
      <th>Yuma</th>
      <td> 70</td>
      <td>   Amy</td>
      <td>  3</td>
      <td> 2014</td>
    </tr>
    <tr>
      <th>Maricopa</th>
      <td> 62</td>
      <td>  Jake</td>
      <td>  2</td>
      <td> 2014</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 4 columns</p>
</div>



### Sort the dataframe's rows by coverage and then by reports, in ascending order


```python
df.sort_index(by=['coverage', 'reports'])
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>coverage</th>
      <th>name</th>
      <th>reports</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Cochice</th>
      <td> 25</td>
      <td> Jason</td>
      <td>  4</td>
      <td> 2012</td>
    </tr>
    <tr>
      <th>Santa Cruz</th>
      <td> 57</td>
      <td>  Tina</td>
      <td> 31</td>
      <td> 2013</td>
    </tr>
    <tr>
      <th>Maricopa</th>
      <td> 62</td>
      <td>  Jake</td>
      <td>  2</td>
      <td> 2014</td>
    </tr>
    <tr>
      <th>Yuma</th>
      <td> 70</td>
      <td>   Amy</td>
      <td>  3</td>
      <td> 2014</td>
    </tr>
    <tr>
      <th>Pima</th>
      <td> 94</td>
      <td> Molly</td>
      <td> 24</td>
      <td> 2012</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 4 columns</p>
</div>


