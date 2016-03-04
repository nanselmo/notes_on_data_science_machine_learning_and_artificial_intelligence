Title: Battle of Five Kings Dataset
Slug: dataset_war_of_five_kings
Summary: Battle of Five Kings Dataset
Date: 2016-12-01 12:00
Category: Python
Tags: Basics
Authors: Chris Albon




```python
# Import modules
import pandas as pd

# Set ipython's max row display
pd.set_option('display.max_row', 1000)

# Set iPython's max column width to 50
pd.set_option('display.max_columns', 50)
```


```python
df = pd.read_csv('https://www.dropbox.com/s/52cb7kcflr8qm2u/5kings_battles_v1.csv?dl=1')
df.head()
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>year</th>
      <th>battle_number</th>
      <th>attacker_king</th>
      <th>defender_king</th>
      <th>attacker_1</th>
      <th>attacker_2</th>
      <th>attacker_3</th>
      <th>attacker_4</th>
      <th>defender_1</th>
      <th>defender_2</th>
      <th>defender_3</th>
      <th>defender_4</th>
      <th>attacker_outcome</th>
      <th>battle_type</th>
      <th>major_death</th>
      <th>major_capture</th>
      <th>attacker_size</th>
      <th>defender_size</th>
      <th>attacker_commander</th>
      <th>defender_commander</th>
      <th>summer</th>
      <th>location</th>
      <th>region</th>
      <th>note</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>    Battle of the Golden Tooth</td>
      <td> 298</td>
      <td> 1</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td>               Robb Stark</td>
      <td> Lannister</td>
      <td>   NaN</td>
      <td> NaN</td>
      <td> NaN</td>
      <td>     Tully</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>  win</td>
      <td> pitched battle</td>
      <td> 1</td>
      <td> 0</td>
      <td> 15000</td>
      <td>  4000</td>
      <td>                                   Jaime Lannister</td>
      <td>                              Clement Piper, Vance</td>
      <td> 1</td>
      <td>    Golden Tooth</td>
      <td> The Westerlands</td>
      <td> NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>   Battle at the Mummer's Ford</td>
      <td> 298</td>
      <td> 2</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td>               Robb Stark</td>
      <td> Lannister</td>
      <td>   NaN</td>
      <td> NaN</td>
      <td> NaN</td>
      <td> Baratheon</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>  win</td>
      <td>         ambush</td>
      <td> 1</td>
      <td> 0</td>
      <td>   NaN</td>
      <td>   120</td>
      <td>                                    Gregor Clegane</td>
      <td>                                  Beric Dondarrion</td>
      <td> 1</td>
      <td>   Mummer's Ford</td>
      <td>  The Riverlands</td>
      <td> NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>            Battle of Riverrun</td>
      <td> 298</td>
      <td> 3</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td>               Robb Stark</td>
      <td> Lannister</td>
      <td>   NaN</td>
      <td> NaN</td>
      <td> NaN</td>
      <td>     Tully</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>  win</td>
      <td> pitched battle</td>
      <td> 0</td>
      <td> 1</td>
      <td> 15000</td>
      <td> 10000</td>
      <td>                      Jaime Lannister, Andros Brax</td>
      <td>                     Edmure Tully, Tytos Blackwood</td>
      <td> 1</td>
      <td>        Riverrun</td>
      <td>  The Riverlands</td>
      <td> NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>      Battle of the Green Fork</td>
      <td> 298</td>
      <td> 4</td>
      <td>               Robb Stark</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td>     Stark</td>
      <td>   NaN</td>
      <td> NaN</td>
      <td> NaN</td>
      <td> Lannister</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> loss</td>
      <td> pitched battle</td>
      <td> 1</td>
      <td> 1</td>
      <td> 18000</td>
      <td> 20000</td>
      <td> Roose Bolton, Wylis Manderly, Medger Cerwyn, H...</td>
      <td> Tywin Lannister, Gregor Clegane, Kevan Lannist...</td>
      <td> 1</td>
      <td>      Green Fork</td>
      <td>  The Riverlands</td>
      <td> NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td> Battle of the Whispering Wood</td>
      <td> 298</td>
      <td> 5</td>
      <td>               Robb Stark</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td>     Stark</td>
      <td> Tully</td>
      <td> NaN</td>
      <td> NaN</td>
      <td> Lannister</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>  win</td>
      <td>         ambush</td>
      <td> 1</td>
      <td> 1</td>
      <td>  1875</td>
      <td>  6000</td>
      <td>                         Robb Stark, Brynden Tully</td>
      <td>                                   Jaime Lannister</td>
      <td> 1</td>
      <td> Whispering Wood</td>
      <td>  The Riverlands</td>
      <td> NaN</td>
    </tr>
  </tbody>
</table>
</div>


