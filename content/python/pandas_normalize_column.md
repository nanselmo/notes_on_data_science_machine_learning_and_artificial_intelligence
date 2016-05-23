Title: Normalize A Column In Pandas
Slug: pandas_normalize_column
Summary: Normalize A Column In Pandas
Date: 2016-05-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon



**Note:** Based on: [Sandman via StackOverflow](http://stackoverflow.com/questions/26414913/normalize-rows-of-pandas-data-frame).

## Preliminaries


```python
# Import required modules
import pandas as pd
from sklearn import preprocessing

# Set charts to view inline
%matplotlib inline
```

## Create Unnormalized Data


```python
# Create an example dataframe with a column of unnormalized data
data = {'score': [234,24,14,27,-74,46,73,-18,59,160]}
df = pd.DataFrame(data)
df
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>234</td>
    </tr>
    <tr>
      <th>1</th>
      <td>24</td>
    </tr>
    <tr>
      <th>2</th>
      <td>14</td>
    </tr>
    <tr>
      <th>3</th>
      <td>27</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-74</td>
    </tr>
    <tr>
      <th>5</th>
      <td>46</td>
    </tr>
    <tr>
      <th>6</th>
      <td>73</td>
    </tr>
    <tr>
      <th>7</th>
      <td>-18</td>
    </tr>
    <tr>
      <th>8</th>
      <td>59</td>
    </tr>
    <tr>
      <th>9</th>
      <td>160</td>
    </tr>
  </tbody>
</table>
</div>




```python
# View the unnormalized data
df['score'].plot(kind='bar')
```




    <matplotlib.axes._subplots.AxesSubplot at 0x109525e48>




![png]({filename}/images/pandas_normalize_column/output_5_1.png)


## Normalize The Column


```python
# Create x, where x the 'scores' column's values as floats
x = df['score'].values.astype(float)

# Create a minimum and maximum processor object
min_max_scaler = preprocessing.MinMaxScaler()

# Create an object to transform the data to fit minmax processor
x_scaled = min_max_scaler.fit_transform(x)

# Run the normalizer on the dataframe
df_normalized = pd.DataFrame(x_scaled)
```


```python
# View the dataframe
df_normalized
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.318182</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.285714</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.327922</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0.389610</td>
    </tr>
    <tr>
      <th>6</th>
      <td>0.477273</td>
    </tr>
    <tr>
      <th>7</th>
      <td>0.181818</td>
    </tr>
    <tr>
      <th>8</th>
      <td>0.431818</td>
    </tr>
    <tr>
      <th>9</th>
      <td>0.759740</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Plot the dataframe
df_normalized.plot(kind='bar')
```




    <matplotlib.axes._subplots.AxesSubplot at 0x10956add8>




![png]({filename}/images/pandas_normalize_column/output_9_1.png)

