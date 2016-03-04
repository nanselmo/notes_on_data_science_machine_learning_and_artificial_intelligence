Title: Selecting Pandas DataFrame Rows Based On Conditions
Slug: pandas_selecting_rows_on_conditions
Summary: Selecting Pandas DataFrame Rows Based On Conditions
Date: 2016-12-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon



## Preliminaries


```python
# Import modules
import pandas as pd

# Set ipython's max row display
pd.set_option('display.max_row', 1000)

# Set iPython's max column width to 50
pd.set_option('display.max_columns', 50)
```


```python
# Load example dataset
df = pd.read_csv('https://www.dropbox.com/s/52cb7kcflr8qm2u/5kings_battles_v1.csv?dl=1')
```

## Method 1: Using Boolean Variables


```python
# Create variable with TRUE if stark is the attacker
stark_attacker = df['attacker_king'] == "Robb Stark"

# Create variable with TRUE if the attacker wins
attacker_wins = df['attacker_outcome'] == "win"

# Select all cases where stark is the attacker and the attacker wins
df[stark_attacker & attacker_wins]
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
      <th>4 </th>
      <td> Battle of the Whispering Wood</td>
      <td> 298</td>
      <td>  5</td>
      <td> Robb Stark</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td> Stark</td>
      <td> Tully</td>
      <td> NaN</td>
      <td> NaN</td>
      <td> Lannister</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> win</td>
      <td>         ambush</td>
      <td> 1</td>
      <td> 1</td>
      <td> 1875</td>
      <td>  6000</td>
      <td>                     Robb Stark, Brynden Tully</td>
      <td>                                   Jaime Lannister</td>
      <td> 1</td>
      <td>  Whispering Wood</td>
      <td>  The Riverlands</td>
      <td>                                               NaN</td>
    </tr>
    <tr>
      <th>5 </th>
      <td>           Battle of the Camps</td>
      <td> 298</td>
      <td>  6</td>
      <td> Robb Stark</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td> Stark</td>
      <td> Tully</td>
      <td> NaN</td>
      <td> NaN</td>
      <td> Lannister</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> win</td>
      <td>         ambush</td>
      <td> 0</td>
      <td> 0</td>
      <td> 6000</td>
      <td> 12625</td>
      <td>    Robb Stark, Tytos Blackwood, Brynden Tully</td>
      <td>                  Lord Andros Brax, Forley Prester</td>
      <td> 1</td>
      <td>         Riverrun</td>
      <td>  The Riverlands</td>
      <td>                                               NaN</td>
    </tr>
    <tr>
      <th>10</th>
      <td>    Battle of Torrhen's Square</td>
      <td> 299</td>
      <td> 11</td>
      <td> Robb Stark</td>
      <td>      Balon/Euron Greyjoy</td>
      <td> Stark</td>
      <td>   NaN</td>
      <td> NaN</td>
      <td> NaN</td>
      <td>   Greyjoy</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> win</td>
      <td> pitched battle</td>
      <td> 0</td>
      <td> 0</td>
      <td>  244</td>
      <td>   900</td>
      <td>                    Rodrik Cassel, Cley Cerwyn</td>
      <td>                                   Dagmer Cleftjaw</td>
      <td> 1</td>
      <td> Torrhen's Square</td>
      <td>       The North</td>
      <td> Greyjoy's troop number comes from the 264 esti...</td>
    </tr>
    <tr>
      <th>14</th>
      <td>             Battle of Oxcross</td>
      <td> 299</td>
      <td> 15</td>
      <td> Robb Stark</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td> Stark</td>
      <td> Tully</td>
      <td> NaN</td>
      <td> NaN</td>
      <td> Lannister</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> win</td>
      <td>         ambush</td>
      <td> 1</td>
      <td> 1</td>
      <td> 6000</td>
      <td> 10000</td>
      <td>                     Robb Stark, Brynden Tully</td>
      <td> Stafford Lannister, Roland Crakehall, Antario ...</td>
      <td> 1</td>
      <td>          Oxcross</td>
      <td> The Westerlands</td>
      <td>                                               NaN</td>
    </tr>
    <tr>
      <th>17</th>
      <td>             Sack of Harrenhal</td>
      <td> 299</td>
      <td> 18</td>
      <td> Robb Stark</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td> Stark</td>
      <td>   NaN</td>
      <td> NaN</td>
      <td> NaN</td>
      <td> Lannister</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> win</td>
      <td>         ambush</td>
      <td> 1</td>
      <td> 0</td>
      <td>  100</td>
      <td>   100</td>
      <td>       Roose Bolton, Vargo Hoat, Robett Glover</td>
      <td>                                       Amory Lorch</td>
      <td> 1</td>
      <td>        Harrenhal</td>
      <td>  The Riverlands</td>
      <td>                                               NaN</td>
    </tr>
    <tr>
      <th>18</th>
      <td>            Battle of the Crag</td>
      <td> 299</td>
      <td> 19</td>
      <td> Robb Stark</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td> Stark</td>
      <td>   NaN</td>
      <td> NaN</td>
      <td> NaN</td>
      <td> Lannister</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> win</td>
      <td>         ambush</td>
      <td> 0</td>
      <td> 0</td>
      <td> 6000</td>
      <td>   NaN</td>
      <td> Robb Stark, Smalljon Umber, Black Walder Frey</td>
      <td>                                      Rolph Spicer</td>
      <td> 1</td>
      <td>             Crag</td>
      <td> The Westerlands</td>
      <td>                                               NaN</td>
    </tr>
    <tr>
      <th>20</th>
      <td>                Siege of Darry</td>
      <td> 299</td>
      <td> 21</td>
      <td> Robb Stark</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td> Darry</td>
      <td>   NaN</td>
      <td> NaN</td>
      <td> NaN</td>
      <td> Lannister</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> win</td>
      <td>          siege</td>
      <td> 0</td>
      <td> 0</td>
      <td>  NaN</td>
      <td>   NaN</td>
      <td>                               Helman Tallhart</td>
      <td>                                               NaN</td>
      <td> 1</td>
      <td>            Darry</td>
      <td>  The Riverlands</td>
      <td>                                               NaN</td>
    </tr>
    <tr>
      <th>26</th>
      <td>              Siege of Seagard</td>
      <td> 299</td>
      <td> 27</td>
      <td> Robb Stark</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td>  Frey</td>
      <td>   NaN</td>
      <td> NaN</td>
      <td> NaN</td>
      <td> Mallister</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> win</td>
      <td>          siege</td>
      <td> 0</td>
      <td> 1</td>
      <td>  NaN</td>
      <td>   NaN</td>
      <td>                                   Walder Frey</td>
      <td>                                   Jason Mallister</td>
      <td> 1</td>
      <td>          Seagard</td>
      <td>  The Riverlands</td>
      <td>                                               NaN</td>
    </tr>
  </tbody>
</table>
</div>



## Method 2: Using variable attributes 


```python
# Select the rows where attacker_2 is not missing, and defender_2 is not missing
df[df['attacker_2'].notnull() & df['defender_2'].notnull()]
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
      <th>27</th>
      <td> Battle of Castle Black</td>
      <td> 300</td>
      <td> 28</td>
      <td> Stannis Baratheon</td>
      <td>             Mance Rayder</td>
      <td> Free folk</td>
      <td>   Thenns</td>
      <td>  Giants</td>
      <td>    NaN</td>
      <td> Night's Watch</td>
      <td> Baratheon</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> loss</td>
      <td> siege</td>
      <td>  1</td>
      <td>  1</td>
      <td> 100000</td>
      <td> 1240</td>
      <td> Stannis Baratheon, Jon Snow, Donal Noye, Cotte...</td>
      <td> Mance Rayder, Tormund Giantsbane, Harma Dogshe...</td>
      <td> 0</td>
      <td> Castle Black</td>
      <td> Beyond the Wall</td>
      <td> NaN</td>
    </tr>
    <tr>
      <th>37</th>
      <td>    Siege of Winterfell</td>
      <td> 300</td>
      <td> 38</td>
      <td> Stannis Baratheon</td>
      <td> Joffrey/Tommen Baratheon</td>
      <td> Baratheon</td>
      <td> Karstark</td>
      <td> Mormont</td>
      <td> Glover</td>
      <td>        Bolton</td>
      <td>      Frey</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>  NaN</td>
      <td>   NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>   5000</td>
      <td> 8000</td>
      <td>                                 Stannis Baratheon</td>
      <td>                                      Roose Bolton</td>
      <td> 0</td>
      <td>   Winterfell</td>
      <td>       The North</td>
      <td> NaN</td>
    </tr>
  </tbody>
</table>
</div>


