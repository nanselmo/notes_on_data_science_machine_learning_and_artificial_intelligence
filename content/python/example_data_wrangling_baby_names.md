Title: Creating a list of potential baby names
Slug: example_data_wrangling_baby_names
Summary: Creating a list of potential baby names
Date: 2016-05-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon



## Prelimaries


```python
# Import modules
import pandas as pd
import numpy as np
import os

# Set plots to be inline
%matplotlib inline

# Set ipython's max row display
pd.set_option('display.max_row', 1000)

# Set iPython's max column width to 50
pd.set_option('display.max_columns', 50)
```

## Load the data


```python
# Create a sequence of numbers as a list, from 1880 to 2013
file_number = list(range(1880, 2013, 1))

# Convert the list to a string
file_number = list(map((lambda x: str(x)), file_number))

# View the first five elements of the list
file_number[0:5]
```




    ['1880', '1881', '1882', '1883', '1884']




```python
# Create a dataframe name variable
df_name = []

# Set the iteration counter
i = 0

# For each item in file_number list
for item in file_number:
    # Create a file name that is df_ and the file_number, then attach to df_name
    df_name.append('df_' + str(file_number[i]))
    # Add one to the iteration counter
    i = i+1
```


```python
# View the top five rows of df_name
df_name[0:5]
```




    ['df_1880', 'df_1881', 'df_1882', 'df_1883', 'df_1884']




```python
# Create a list for the file names
file_name = []

# Create the iteration counter
i = 0

# For each item in file number,
for item in file_number:
    # Create a filename that combines, yob the year, and .txt
    file_name.append('yob' + str(file_number[i]) + '.txt')
    # Add 1 to the iteration counter
    i = i+1
```


```python
# View the top five rows of file_name
file_name[0:5]
```




    ['yob1880.txt', 'yob1881.txt', 'yob1882.txt', 'yob1883.txt', 'yob1884.txt']




```python
# Create a file path for the directory where the files are located
file_loc = os.path.abspath("data/names/")
```


```python
# Create a dataframe for the data we will creat in the next step
df = pd.DataFrame()
```


```python
# Create an iteration counter
k = 0

# For each item in df_name,
for item in df_name:
    # Run the command to read the csv using the variables we created previously
    data = pd.read_csv(file_loc+'/'+file_name[k], header=None, names=['name', 'sex', 'count'])
    # Create a variable with the year of the observation
    data['year'] = file_number[k]
    # Concat (i.e. attach) the data to the df
    df = pd.concat([df, data])
    # Add 1 to the iteration counter
    k = k+1
```


```python
# Check the length of the df, just to make sure everything is okay
len(df)
```




    1759019



## Clean the data


```python
# Drop all males (I'm having a daughter!)
df = df[df.sex != 'M'] 
```


```python
# Check the length of the df, we should lose roughly half the observations
len(df)
```




    1043318




```python
# Create a boolean variable that is true when year == 2012 and False otherise
df['2012'] = np.where(df['year'] == '2012', True, False)
```


```python
# Create a variable called df.count_2012 that is df.count when df.2012 is true
df['count_2012'] = df['count'][df['2012']]
```


```python
df.head(3)
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>sex</th>
      <th>count</th>
      <th>year</th>
      <th>2012</th>
      <th>count_2012</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td> Mary</td>
      <td> F</td>
      <td> 7065</td>
      <td> 1880</td>
      <td> False</td>
      <td> 22245</td>
    </tr>
    <tr>
      <th>1</th>
      <td> Anna</td>
      <td> F</td>
      <td> 2604</td>
      <td> 1880</td>
      <td> False</td>
      <td> 20871</td>
    </tr>
    <tr>
      <th>2</th>
      <td> Emma</td>
      <td> F</td>
      <td> 2003</td>
      <td> 1880</td>
      <td> False</td>
      <td> 19026</td>
    </tr>
  </tbody>
</table>
</div>



## Reshape the data into the format we want


```python
# Create a variable that is a pivot table, 
# totalling the number of times a name is registered
names = df.pivot_table(index=['name'], aggfunc=np.sum)
```


```python
# Sort the names variable by their popularity in 2012
names = names.sort(['count_2012'], ascending=[0])
```


```python
# Clean the dataset by dropping the boolean 2012 variable
names = names.drop('2012', axis=1)
```


```python
# Turn the index into its own column
names['names'] = names.index
```


```python
# create a dataframe with all names ending in a
a_names = names[names['names'].str.endswith('a')]
```


```python
# How many names in a_names?
len(a_names)
```




    26687




```python
# Let's find Zaria
a_names[a_names['names'] == 'Zaria']
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>count</th>
      <th>count_2012</th>
      <th>names</th>
    </tr>
    <tr>
      <th>name</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Zaria</th>
      <td> 6892</td>
      <td> 7449</td>
      <td> Zaria</td>
    </tr>
  </tbody>
</table>
</div>



## Export the data


```python
# Export the data to csv
a_names.to_csv('names.csv')
```
