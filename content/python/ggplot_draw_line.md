Title: Draw a line in ggplot
Slug: ggplot_draw_line
Summary: Draw a line in ggplot
Date: 2016-05-01 12:00
Category: Python
Tags: Data Visualization
Authors: Chris Albon




```python
# Import required modules
from ggplot import *
%matplotlib inline
import pandas as pd
```


```python
# Create a dataset of battle data
data = {'battle': ['Battle of Two Forks', 'Battle of Cochise', 'Battle of Bells', 'Battle of the Beach', 'Battle of Flatlander', 'Battle of Middorin', 'Battle of Massai', 'Battle of Monogrop', 'Battle of ', 'Battle of Sticks'], 
        'season': ['winter', 'fall', 'fall', 'fall', 'spring', 'winter', 'summer', 'winter', 'summer', 'summer'],
        'terrain': ['mountains', 'mountains', 'mountains', 'beach', 'beach', 'plains', 'plains', 'city', 'city', 'city'],
        'weather': ['rain', 'rain', 'cloudy', 'sunny', 'rain', 'rain', 'sunny', 'cloudy', 'rain', 'sunny'],
        'victor': ['attacker', 'defender', 'attacker', 'defender', 'attacker', 'defender', 'attacker', 'defender', 'attacker', 'defender'],
        'deaths_attacker': [425, 242, 323, 223, 783, 436, 324, 3321, 262, 843],
        'deaths_defender': [423, 264, 1231, 23, 23, 42, 124, 631, 232, 213],
        'wounded_attacker': [41, 214, 131, 12, 123, 124, 264, 311, 132, 623],
        'wounded_defender': [14, 1424, 131, 12, 34, 124, 1124, 1431, 122, 2563],
        'soldiers_attacker': [2532, 6346, 3341, 6732, 12563, 2356, 253, 5277, 2732, 6278],
        'soldiers_defender': [37235, 2523, 2133, 1245, 2671, 7832, 2622, 3331, 2522, 26773]}
df = pd.DataFrame(data)
df
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>battle</th>
      <th>deaths_attacker</th>
      <th>deaths_defender</th>
      <th>season</th>
      <th>soldiers_attacker</th>
      <th>soldiers_defender</th>
      <th>terrain</th>
      <th>victor</th>
      <th>weather</th>
      <th>wounded_attacker</th>
      <th>wounded_defender</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>  Battle of Two Forks</td>
      <td>  425</td>
      <td>  423</td>
      <td> winter</td>
      <td>  2532</td>
      <td> 37235</td>
      <td> mountains</td>
      <td> attacker</td>
      <td>   rain</td>
      <td>  41</td>
      <td>   14</td>
    </tr>
    <tr>
      <th>1</th>
      <td>    Battle of Cochise</td>
      <td>  242</td>
      <td>  264</td>
      <td>   fall</td>
      <td>  6346</td>
      <td>  2523</td>
      <td> mountains</td>
      <td> defender</td>
      <td>   rain</td>
      <td> 214</td>
      <td> 1424</td>
    </tr>
    <tr>
      <th>2</th>
      <td>      Battle of Bells</td>
      <td>  323</td>
      <td> 1231</td>
      <td>   fall</td>
      <td>  3341</td>
      <td>  2133</td>
      <td> mountains</td>
      <td> attacker</td>
      <td> cloudy</td>
      <td> 131</td>
      <td>  131</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Battle of the Beach</td>
      <td>  223</td>
      <td>   23</td>
      <td>   fall</td>
      <td>  6732</td>
      <td>  1245</td>
      <td>     beach</td>
      <td> defender</td>
      <td>  sunny</td>
      <td>  12</td>
      <td>   12</td>
    </tr>
    <tr>
      <th>4</th>
      <td> Battle of Flatlander</td>
      <td>  783</td>
      <td>   23</td>
      <td> spring</td>
      <td> 12563</td>
      <td>  2671</td>
      <td>     beach</td>
      <td> attacker</td>
      <td>   rain</td>
      <td> 123</td>
      <td>   34</td>
    </tr>
    <tr>
      <th>5</th>
      <td>   Battle of Middorin</td>
      <td>  436</td>
      <td>   42</td>
      <td> winter</td>
      <td>  2356</td>
      <td>  7832</td>
      <td>    plains</td>
      <td> defender</td>
      <td>   rain</td>
      <td> 124</td>
      <td>  124</td>
    </tr>
    <tr>
      <th>6</th>
      <td>     Battle of Massai</td>
      <td>  324</td>
      <td>  124</td>
      <td> summer</td>
      <td>   253</td>
      <td>  2622</td>
      <td>    plains</td>
      <td> attacker</td>
      <td>  sunny</td>
      <td> 264</td>
      <td> 1124</td>
    </tr>
    <tr>
      <th>7</th>
      <td>   Battle of Monogrop</td>
      <td> 3321</td>
      <td>  631</td>
      <td> winter</td>
      <td>  5277</td>
      <td>  3331</td>
      <td>      city</td>
      <td> defender</td>
      <td> cloudy</td>
      <td> 311</td>
      <td> 1431</td>
    </tr>
    <tr>
      <th>8</th>
      <td>           Battle of </td>
      <td>  262</td>
      <td>  232</td>
      <td> summer</td>
      <td>  2732</td>
      <td>  2522</td>
      <td>      city</td>
      <td> attacker</td>
      <td>   rain</td>
      <td> 132</td>
      <td>  122</td>
    </tr>
    <tr>
      <th>9</th>
      <td>     Battle of Sticks</td>
      <td>  843</td>
      <td>  213</td>
      <td> summer</td>
      <td>  6278</td>
      <td> 26773</td>
      <td>      city</td>
      <td> defender</td>
      <td>  sunny</td>
      <td> 623</td>
      <td> 2563</td>
    </tr>
  </tbody>
</table>
</div>




```python
# scatterplot of attacker deaths vs defender deaths, with a line specified by slope and intercept
ggplot(df, aes(x='deaths_attacker', y='deaths_defender')) + \
    geom_point() + \
    geom_abline(intercept=100, slope=0, colour="red")
```


![png]({filename}/images/ggplot_draw_line/output_3_0.png)





    <ggplot: (279504957)>


