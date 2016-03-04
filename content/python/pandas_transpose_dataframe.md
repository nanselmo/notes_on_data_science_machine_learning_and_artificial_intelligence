Title: Transpose A Dataframe In Pandas
Slug: pandas_transpose_dataframe
Summary: Transpose A Dataframe In Pandas
Date: 2016-12-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon




```python
# Import Preliminaries
import pandas as pd
```


```python
# Create a dataset with the index being a set of names
raw_data = {'regiment': ['Nighthawks', 'Nighthawks', 'Nighthawks', 'Nighthawks', 'Dragoons', 'Dragoons', 'Dragoons', 'Dragoons', 'Scouts', 'Scouts', 'Scouts', 'Scouts'], 
        'company': ['1st', '1st', '2nd', '2nd', '1st', '1st', '2nd', '2nd','1st', '1st', '2nd', '2nd'], 
        'name': ['Miller', 'Jacobson', 'Ali', 'Milner', 'Cooze', 'Jacon', 'Ryaner', 'Sone', 'Sloan', 'Piger', 'Riani', 'Ali'], 
        'preTestScore': [4, 24, 31, 2, 3, 4, 24, 31, 2, 3, 2, 3],
        'postTestScore': [25, 94, 57, 62, 70, 25, 94, 57, 62, 70, 62, 70]}
df = pd.DataFrame(raw_data, columns = ['regiment', 'company', 'name', 'preTestScore', 'postTestScore'], index=df.name)
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
    <tr>
      <th>name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Miller</th>
      <td> Nighthawks</td>
      <td> 1st</td>
      <td>   Miller</td>
      <td>  4</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>Jacobson</th>
      <td> Nighthawks</td>
      <td> 1st</td>
      <td> Jacobson</td>
      <td> 24</td>
      <td> 94</td>
    </tr>
    <tr>
      <th>Ali</th>
      <td> Nighthawks</td>
      <td> 2nd</td>
      <td>      Ali</td>
      <td> 31</td>
      <td> 57</td>
    </tr>
    <tr>
      <th>Milner</th>
      <td> Nighthawks</td>
      <td> 2nd</td>
      <td>   Milner</td>
      <td>  2</td>
      <td> 62</td>
    </tr>
    <tr>
      <th>Cooze</th>
      <td>   Dragoons</td>
      <td> 1st</td>
      <td>    Cooze</td>
      <td>  3</td>
      <td> 70</td>
    </tr>
    <tr>
      <th>Jacon</th>
      <td>   Dragoons</td>
      <td> 1st</td>
      <td>    Jacon</td>
      <td>  4</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>Ryaner</th>
      <td>   Dragoons</td>
      <td> 2nd</td>
      <td>   Ryaner</td>
      <td> 24</td>
      <td> 94</td>
    </tr>
    <tr>
      <th>Sone</th>
      <td>   Dragoons</td>
      <td> 2nd</td>
      <td>     Sone</td>
      <td> 31</td>
      <td> 57</td>
    </tr>
    <tr>
      <th>Sloan</th>
      <td>     Scouts</td>
      <td> 1st</td>
      <td>    Sloan</td>
      <td>  2</td>
      <td> 62</td>
    </tr>
    <tr>
      <th>Piger</th>
      <td>     Scouts</td>
      <td> 1st</td>
      <td>    Piger</td>
      <td>  3</td>
      <td> 70</td>
    </tr>
    <tr>
      <th>Riani</th>
      <td>     Scouts</td>
      <td> 2nd</td>
      <td>    Riani</td>
      <td>  2</td>
      <td> 62</td>
    </tr>
    <tr>
      <th>Ali</th>
      <td>     Scouts</td>
      <td> 2nd</td>
      <td>      Ali</td>
      <td>  3</td>
      <td> 70</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Transpose the dataset, so that the index (in this case the names) are columns
df.transpose()
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>name</th>
      <th>Miller</th>
      <th>Jacobson</th>
      <th>Ali</th>
      <th>Milner</th>
      <th>Cooze</th>
      <th>Jacon</th>
      <th>Ryaner</th>
      <th>Sone</th>
      <th>Sloan</th>
      <th>Piger</th>
      <th>Riani</th>
      <th>Ali</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>regiment</th>
      <td> Nighthawks</td>
      <td> Nighthawks</td>
      <td> Nighthawks</td>
      <td> Nighthawks</td>
      <td> Dragoons</td>
      <td> Dragoons</td>
      <td> Dragoons</td>
      <td> Dragoons</td>
      <td> Scouts</td>
      <td> Scouts</td>
      <td> Scouts</td>
      <td> Scouts</td>
    </tr>
    <tr>
      <th>company</th>
      <td>        1st</td>
      <td>        1st</td>
      <td>        2nd</td>
      <td>        2nd</td>
      <td>      1st</td>
      <td>      1st</td>
      <td>      2nd</td>
      <td>      2nd</td>
      <td>    1st</td>
      <td>    1st</td>
      <td>    2nd</td>
      <td>    2nd</td>
    </tr>
    <tr>
      <th>name</th>
      <td>     Miller</td>
      <td>   Jacobson</td>
      <td>        Ali</td>
      <td>     Milner</td>
      <td>    Cooze</td>
      <td>    Jacon</td>
      <td>   Ryaner</td>
      <td>     Sone</td>
      <td>  Sloan</td>
      <td>  Piger</td>
      <td>  Riani</td>
      <td>    Ali</td>
    </tr>
    <tr>
      <th>preTestScore</th>
      <td>          4</td>
      <td>         24</td>
      <td>         31</td>
      <td>          2</td>
      <td>        3</td>
      <td>        4</td>
      <td>       24</td>
      <td>       31</td>
      <td>      2</td>
      <td>      3</td>
      <td>      2</td>
      <td>      3</td>
    </tr>
    <tr>
      <th>postTestScore</th>
      <td>         25</td>
      <td>         94</td>
      <td>         57</td>
      <td>         62</td>
      <td>       70</td>
      <td>       25</td>
      <td>       94</td>
      <td>       57</td>
      <td>     62</td>
      <td>     70</td>
      <td>     62</td>
      <td>     70</td>
    </tr>
  </tbody>
</table>
</div>


