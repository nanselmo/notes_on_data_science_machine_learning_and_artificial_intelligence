Title: Pivot Tables In Pandas
Slug: pandas_pivot_tables
Summary: Pivot Tables In Pandas
Date: 2016-05-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon



### import modules


```python
import pandas as pd
```

### Create dataframe


```python
raw_data = {'regiment': ['Nighthawks', 'Nighthawks', 'Nighthawks', 'Nighthawks', 'Dragoons', 'Dragoons', 'Dragoons', 'Dragoons', 'Scouts', 'Scouts', 'Scouts', 'Scouts'], 
        'company': ['1st', '1st', '2nd', '2nd', '1st', '1st', '2nd', '2nd','1st', '1st', '2nd', '2nd'], 
        'name': ['Miller', 'Jacobson', 'Ali', 'Milner', 'Cooze', 'Jacon', 'Ryaner', 'Sone', 'Sloan', 'Piger', 'Riani', 'Ali'], 
        'preTestScore': [4, 24, 31, 2, 3, 4, 24, 31, 2, 3, 2, 3],
        'postTestScore': [25, 94, 57, 62, 70, 25, 94, 57, 62, 70, 62, 70]}
df = pd.DataFrame(raw_data, columns = ['regiment', 'company', 'name', 'preTestScore', 'postTestScore'])
df
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>regiment</th>
      <th>company</th>
      <th>name</th>
      <th>preTestScore</th>
      <th>postTestScore</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0 </th>
      <td> Nighthawks</td>
      <td> 1st</td>
      <td>   Miller</td>
      <td>  4</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>1 </th>
      <td> Nighthawks</td>
      <td> 1st</td>
      <td> Jacobson</td>
      <td> 24</td>
      <td> 94</td>
    </tr>
    <tr>
      <th>2 </th>
      <td> Nighthawks</td>
      <td> 2nd</td>
      <td>      Ali</td>
      <td> 31</td>
      <td> 57</td>
    </tr>
    <tr>
      <th>3 </th>
      <td> Nighthawks</td>
      <td> 2nd</td>
      <td>   Milner</td>
      <td>  2</td>
      <td> 62</td>
    </tr>
    <tr>
      <th>4 </th>
      <td>   Dragoons</td>
      <td> 1st</td>
      <td>    Cooze</td>
      <td>  3</td>
      <td> 70</td>
    </tr>
    <tr>
      <th>5 </th>
      <td>   Dragoons</td>
      <td> 1st</td>
      <td>    Jacon</td>
      <td>  4</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>6 </th>
      <td>   Dragoons</td>
      <td> 2nd</td>
      <td>   Ryaner</td>
      <td> 24</td>
      <td> 94</td>
    </tr>
    <tr>
      <th>7 </th>
      <td>   Dragoons</td>
      <td> 2nd</td>
      <td>     Sone</td>
      <td> 31</td>
      <td> 57</td>
    </tr>
    <tr>
      <th>8 </th>
      <td>     Scouts</td>
      <td> 1st</td>
      <td>    Sloan</td>
      <td>  2</td>
      <td> 62</td>
    </tr>
    <tr>
      <th>9 </th>
      <td>     Scouts</td>
      <td> 1st</td>
      <td>    Piger</td>
      <td>  3</td>
      <td> 70</td>
    </tr>
    <tr>
      <th>10</th>
      <td>     Scouts</td>
      <td> 2nd</td>
      <td>    Riani</td>
      <td>  2</td>
      <td> 62</td>
    </tr>
    <tr>
      <th>11</th>
      <td>     Scouts</td>
      <td> 2nd</td>
      <td>      Ali</td>
      <td>  3</td>
      <td> 70</td>
    </tr>
  </tbody>
</table>
<p>12 rows × 5 columns</p>
</div>



### Create a pivot table of group means, by company and regiment


```python
df.pivot_table(rows=['regiment','company'])
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>postTestScore</th>
      <th>preTestScore</th>
    </tr>
    <tr>
      <th>regiment</th>
      <th>company</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="2" valign="top">Dragoons</th>
      <th>1st</th>
      <td> 47.5</td>
      <td>  3.5</td>
    </tr>
    <tr>
      <th>2nd</th>
      <td> 75.5</td>
      <td> 27.5</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">Nighthawks</th>
      <th>1st</th>
      <td> 59.5</td>
      <td> 14.0</td>
    </tr>
    <tr>
      <th>2nd</th>
      <td> 59.5</td>
      <td> 16.5</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">Scouts</th>
      <th>1st</th>
      <td> 66.0</td>
      <td>  2.5</td>
    </tr>
    <tr>
      <th>2nd</th>
      <td> 66.0</td>
      <td>  2.5</td>
    </tr>
  </tbody>
</table>
<p>6 rows × 2 columns</p>
</div>



### Create a pivot table of group score counts, by company and regimensts


```python
df.pivot_table(rows=['regiment','company'], aggfunc='count')
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th>company</th>
      <th>name</th>
      <th>postTestScore</th>
      <th>preTestScore</th>
      <th>regiment</th>
    </tr>
    <tr>
      <th>regiment</th>
      <th>company</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="2" valign="top">Dragoons</th>
      <th>1st</th>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
    </tr>
    <tr>
      <th>2nd</th>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">Nighthawks</th>
      <th>1st</th>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
    </tr>
    <tr>
      <th>2nd</th>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">Scouts</th>
      <th>1st</th>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
    </tr>
    <tr>
      <th>2nd</th>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
      <td> 2</td>
    </tr>
  </tbody>
</table>
<p>6 rows × 5 columns</p>
</div>


