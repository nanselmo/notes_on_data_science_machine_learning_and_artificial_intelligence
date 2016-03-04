Title: Prussian Horse Kick Data
Slug: dataset_prussian_horse_kicks
Summary: Prussian Horse Kick Data
Date: 2016-12-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon



[Original description](http://www.math.uah.edu/stat/data/HorseKicks.html): "The data above give the number of soilders in the Prussian cavalry killed by horse kicks, by corp membership and by year. The years are from 1875 to 1894, and there are 14 different cavalry corps: the first column corresponds to the guard corp and the other columns to corps 1 through 11, 14, and 15. The data are from Distributome project and are derived from the book by Andrews and Herzberg. The original source of the data is the classic book by von Bortkiewicz (references are given below). The data are famous because they seem to fit the Poisson model reasonably well."

### Import the pandas module


```python
import pandas as pd
```

### Create all the columns of the dataframe as series (called vectors in R)


```python
year = pd.Series([1875, 1876, 1877, 1878, 1879, 1880, 1881, 1882, 1883, 1884, 
                  1885, 1886, 1887, 1888, 1889, 1890, 1891, 1892, 1893, 1894])
guard_corps = pd.Series([0,2,2,1,0,0,1,1,0,3,0,2,1,0,0,1,0,1,0,1])
corps_1 = pd.Series([0,0,0,2,0,3,0,2,0,0,0,1,1,1,0,2,0,3,1,0])
corps_2 = pd.Series([0,0,0,2,0,2,0,0,1,1,0,0,2,1,1,0,0,2,0,0])
corps_3 = pd.Series([0,0,0,1,1,1,2,0,2,0,0,0,1,0,1,2,1,0,0,0])
corps_4 = pd.Series([0,1,0,1,1,1,1,0,0,0,0,1,0,0,0,0,1,1,0,0])
corps_5 = pd.Series([0,0,0,0,2,1,0,0,1,0,0,1,0,1,1,1,1,1,1,0])
corps_6 = pd.Series([0,0,1,0,2,0,0,1,2,0,1,1,3,1,1,1,0,3,0,0])
corps_7 = pd.Series([1,0,1,0,0,0,1,0,1,1,0,0,2,0,0,2,1,0,2,0])
corps_8 = pd.Series([1,0,0,0,1,0,0,1,0,0,0,0,1,0,0,0,1,1,0,1])
corps_9 = pd.Series([0,0,0,0,0,2,1,1,1,0,2,1,1,0,1,2,0,1,0,0])
corps_10 = pd.Series([0,0,1,1,0,1,0,2,0,2,0,0,0,0,2,1,3,0,1,1])
corps_11 = pd.Series([0,0,0,0,2,4,0,1,3,0,1,1,1,1,2,1,3,1,3,1])
corps_14 = pd.Series([ 1,1,2,1,1,3,0,4,0,1,0,3,2,1,0,2,1,1,0,0])
corps_15 = pd.Series([0,1,0,0,0,0,0,1,0,1,1,0,0,0,2,2,0,0,0,0])
```

### Create a dictionary variable that assigns variable names


```python
variables = dict(year = year, guard_corps = guard_corps, corps_1 = corps_1, 
                 corps_2 = corps_2, corps_3 = corps_3, corps_4 = corps_4, 
                 corps_5 = corps_5, corps_6 = corps_6, corps_7 = corps_7, 
                 corps_8 = corps_8, corps_9 = corps_9, corps_10 = corps_10, 
                 corps_11 = corps_11 , corps_14 = corps_14, corps_15 = corps_15)
```

### Create a dataframe and set the order of the columns using the columns attribute


```python
horsekick_data = pd.DataFrame(variables, columns = ['year', 'guard_corps', 
                                                    'corps_1', 'corps_2', 
                                                    'corps_3', 'corps_4', 
                                                    'corps_5', 'corps_6', 
                                                    'corps_7', 'corps_8', 
                                                    'corps_9', 'corps_10', 
                                                    'corps_11', 'corps_14', 
                                                    'corps_15'])
```

### View the dataframe


```python
horsekick_data
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>guard_corps</th>
      <th>corps_1</th>
      <th>corps_2</th>
      <th>corps_3</th>
      <th>corps_4</th>
      <th>corps_5</th>
      <th>corps_6</th>
      <th>corps_7</th>
      <th>corps_8</th>
      <th>corps_9</th>
      <th>corps_10</th>
      <th>corps_11</th>
      <th>corps_14</th>
      <th>corps_15</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0 </th>
      <td> 1875</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>1 </th>
      <td> 1876</td>
      <td> 2</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
    </tr>
    <tr>
      <th>2 </th>
      <td> 1877</td>
      <td> 2</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 2</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>3 </th>
      <td> 1878</td>
      <td> 1</td>
      <td> 2</td>
      <td> 2</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>4 </th>
      <td> 1879</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 2</td>
      <td> 2</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 2</td>
      <td> 1</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>5 </th>
      <td> 1880</td>
      <td> 0</td>
      <td> 3</td>
      <td> 2</td>
      <td> 1</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 2</td>
      <td> 1</td>
      <td> 4</td>
      <td> 3</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>6 </th>
      <td> 1881</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 2</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>7 </th>
      <td> 1882</td>
      <td> 1</td>
      <td> 2</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 2</td>
      <td> 1</td>
      <td> 4</td>
      <td> 1</td>
    </tr>
    <tr>
      <th>8 </th>
      <td> 1883</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 2</td>
      <td> 0</td>
      <td> 1</td>
      <td> 2</td>
      <td> 1</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 3</td>
      <td> 0</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>9 </th>
      <td> 1884</td>
      <td> 3</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 2</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
    </tr>
    <tr>
      <th>10</th>
      <td> 1885</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 2</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 1</td>
    </tr>
    <tr>
      <th>11</th>
      <td> 1886</td>
      <td> 2</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 1</td>
      <td> 3</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>12</th>
      <td> 1887</td>
      <td> 1</td>
      <td> 1</td>
      <td> 2</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 3</td>
      <td> 2</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 1</td>
      <td> 2</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>13</th>
      <td> 1888</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>14</th>
      <td> 1889</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 2</td>
      <td> 2</td>
      <td> 0</td>
      <td> 2</td>
    </tr>
    <tr>
      <th>15</th>
      <td> 1890</td>
      <td> 1</td>
      <td> 2</td>
      <td> 0</td>
      <td> 2</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 2</td>
      <td> 0</td>
      <td> 2</td>
      <td> 1</td>
      <td> 1</td>
      <td> 2</td>
      <td> 2</td>
    </tr>
    <tr>
      <th>16</th>
      <td> 1891</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 3</td>
      <td> 3</td>
      <td> 1</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>17</th>
      <td> 1892</td>
      <td> 1</td>
      <td> 3</td>
      <td> 2</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 3</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>18</th>
      <td> 1893</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 2</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 3</td>
      <td> 0</td>
      <td> 0</td>
    </tr>
    <tr>
      <th>19</th>
      <td> 1894</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 0</td>
      <td> 1</td>
      <td> 0</td>
      <td> 1</td>
      <td> 1</td>
      <td> 0</td>
      <td> 0</td>
    </tr>
  </tbody>
</table>
</div>


