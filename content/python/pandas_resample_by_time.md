Title: Resampling a Time Series in pandas
Slug: pandas_resample_by_time
Summary: Resampling a Time Series in pandas
Date: 2016-05-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon



### Import required modules


```python
import pandas as pd
import numpy as np
```

### Create a dataframe


```python
df = pd.DataFrame()

df['german_army'] = np.random.randint(low=20000, high=30000, size=100)
df['allied_army'] = np.random.randint(low=20000, high=40000, size=100)
df.index = pd.date_range('1/1/2014', periods=100, freq='H')

df.head()
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>german_army</th>
      <th>allied_army</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-01-01 00:00:00</th>
      <td> 21331</td>
      <td> 39348</td>
    </tr>
    <tr>
      <th>2014-01-01 01:00:00</th>
      <td> 27465</td>
      <td> 37775</td>
    </tr>
    <tr>
      <th>2014-01-01 02:00:00</th>
      <td> 20310</td>
      <td> 21410</td>
    </tr>
    <tr>
      <th>2014-01-01 03:00:00</th>
      <td> 22145</td>
      <td> 25203</td>
    </tr>
    <tr>
      <th>2014-01-01 04:00:00</th>
      <td> 22871</td>
      <td> 36609</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 2 columns</p>
</div>



### Truncate the dataframe


```python
df.truncate(before='1/2/2014', after='1/3/2014')
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>german_army</th>
      <th>allied_army</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-01-02 00:00:00</th>
      <td> 27290</td>
      <td> 36896</td>
    </tr>
    <tr>
      <th>2014-01-02 01:00:00</th>
      <td> 26079</td>
      <td> 31298</td>
    </tr>
    <tr>
      <th>2014-01-02 02:00:00</th>
      <td> 28663</td>
      <td> 26045</td>
    </tr>
    <tr>
      <th>2014-01-02 03:00:00</th>
      <td> 23328</td>
      <td> 39686</td>
    </tr>
    <tr>
      <th>2014-01-02 04:00:00</th>
      <td> 25243</td>
      <td> 24545</td>
    </tr>
    <tr>
      <th>2014-01-02 05:00:00</th>
      <td> 29998</td>
      <td> 23463</td>
    </tr>
    <tr>
      <th>2014-01-02 06:00:00</th>
      <td> 22779</td>
      <td> 27992</td>
    </tr>
    <tr>
      <th>2014-01-02 07:00:00</th>
      <td> 25155</td>
      <td> 33747</td>
    </tr>
    <tr>
      <th>2014-01-02 08:00:00</th>
      <td> 29279</td>
      <td> 32127</td>
    </tr>
    <tr>
      <th>2014-01-02 09:00:00</th>
      <td> 23138</td>
      <td> 27684</td>
    </tr>
    <tr>
      <th>2014-01-02 10:00:00</th>
      <td> 24622</td>
      <td> 24583</td>
    </tr>
    <tr>
      <th>2014-01-02 11:00:00</th>
      <td> 29302</td>
      <td> 22012</td>
    </tr>
    <tr>
      <th>2014-01-02 12:00:00</th>
      <td> 29941</td>
      <td> 25643</td>
    </tr>
    <tr>
      <th>2014-01-02 13:00:00</th>
      <td> 28130</td>
      <td> 35022</td>
    </tr>
    <tr>
      <th>2014-01-02 14:00:00</th>
      <td> 26980</td>
      <td> 24659</td>
    </tr>
    <tr>
      <th>2014-01-02 15:00:00</th>
      <td> 20435</td>
      <td> 27753</td>
    </tr>
    <tr>
      <th>2014-01-02 16:00:00</th>
      <td> 29291</td>
      <td> 25136</td>
    </tr>
    <tr>
      <th>2014-01-02 17:00:00</th>
      <td> 24594</td>
      <td> 35866</td>
    </tr>
    <tr>
      <th>2014-01-02 18:00:00</th>
      <td> 28721</td>
      <td> 32888</td>
    </tr>
    <tr>
      <th>2014-01-02 19:00:00</th>
      <td> 23935</td>
      <td> 25330</td>
    </tr>
    <tr>
      <th>2014-01-02 20:00:00</th>
      <td> 22258</td>
      <td> 30980</td>
    </tr>
    <tr>
      <th>2014-01-02 21:00:00</th>
      <td> 22660</td>
      <td> 39378</td>
    </tr>
    <tr>
      <th>2014-01-02 22:00:00</th>
      <td> 24651</td>
      <td> 32796</td>
    </tr>
    <tr>
      <th>2014-01-02 23:00:00</th>
      <td> 26162</td>
      <td> 30592</td>
    </tr>
    <tr>
      <th>2014-01-03 00:00:00</th>
      <td> 21352</td>
      <td> 38357</td>
    </tr>
  </tbody>
</table>
<p>25 rows × 2 columns</p>
</div>



### Set the dataframe's index


```python
df.index = df.index + pd.DateOffset(months=4, days=5)
```

### View the dataframe


```python
df.head()
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>german_army</th>
      <th>allied_army</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-05-06 00:00:00</th>
      <td> 21331</td>
      <td> 39348</td>
    </tr>
    <tr>
      <th>2014-05-06 01:00:00</th>
      <td> 27465</td>
      <td> 37775</td>
    </tr>
    <tr>
      <th>2014-05-06 02:00:00</th>
      <td> 20310</td>
      <td> 21410</td>
    </tr>
    <tr>
      <th>2014-05-06 03:00:00</th>
      <td> 22145</td>
      <td> 25203</td>
    </tr>
    <tr>
      <th>2014-05-06 04:00:00</th>
      <td> 22871</td>
      <td> 36609</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 2 columns</p>
</div>



### Lead a variable 1 hour


```python
df.shift(1).head()
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>german_army</th>
      <th>allied_army</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-05-06 00:00:00</th>
      <td>   NaN</td>
      <td>   NaN</td>
    </tr>
    <tr>
      <th>2014-05-06 01:00:00</th>
      <td> 21331</td>
      <td> 39348</td>
    </tr>
    <tr>
      <th>2014-05-06 02:00:00</th>
      <td> 27465</td>
      <td> 37775</td>
    </tr>
    <tr>
      <th>2014-05-06 03:00:00</th>
      <td> 20310</td>
      <td> 21410</td>
    </tr>
    <tr>
      <th>2014-05-06 04:00:00</th>
      <td> 22145</td>
      <td> 25203</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 2 columns</p>
</div>



### Lag a variable 1 hour


```python
df.shift(-1).tail()
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>german_army</th>
      <th>allied_army</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-05-09 23:00:00</th>
      <td> 28359</td>
      <td> 39177</td>
    </tr>
    <tr>
      <th>2014-05-10 00:00:00</th>
      <td> 27881</td>
      <td> 29686</td>
    </tr>
    <tr>
      <th>2014-05-10 01:00:00</th>
      <td> 26585</td>
      <td> 26210</td>
    </tr>
    <tr>
      <th>2014-05-10 02:00:00</th>
      <td> 22266</td>
      <td> 35398</td>
    </tr>
    <tr>
      <th>2014-05-10 03:00:00</th>
      <td>   NaN</td>
      <td>   NaN</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 2 columns</p>
</div>



### Aggregate into days by summing up the value of each hourly observation


```python
df.resample('D', how='sum')
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>german_army</th>
      <th>allied_army</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-05-06</th>
      <td> 586399</td>
      <td> 722666</td>
    </tr>
    <tr>
      <th>2014-05-07</th>
      <td> 622634</td>
      <td> 716121</td>
    </tr>
    <tr>
      <th>2014-05-08</th>
      <td> 609257</td>
      <td> 781811</td>
    </tr>
    <tr>
      <th>2014-05-09</th>
      <td> 589086</td>
      <td> 672985</td>
    </tr>
    <tr>
      <th>2014-05-10</th>
      <td> 105091</td>
      <td> 130471</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 2 columns</p>
</div>



### Aggregate into days by averaging up the value of each hourly observation


```python
df.resample('D', how='mean')
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>german_army</th>
      <th>allied_army</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-05-06</th>
      <td> 24433.291667</td>
      <td> 30111.083333</td>
    </tr>
    <tr>
      <th>2014-05-07</th>
      <td> 25943.083333</td>
      <td> 29838.375000</td>
    </tr>
    <tr>
      <th>2014-05-08</th>
      <td> 25385.708333</td>
      <td> 32575.458333</td>
    </tr>
    <tr>
      <th>2014-05-09</th>
      <td> 24545.250000</td>
      <td> 28041.041667</td>
    </tr>
    <tr>
      <th>2014-05-10</th>
      <td> 26272.750000</td>
      <td> 32617.750000</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 2 columns</p>
</div>



### Aggregate into days by taking the min value up the value of each hourly observation


```python
df.resample('D', how='min')
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>german_army</th>
      <th>allied_army</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-05-06</th>
      <td> 20310</td>
      <td> 20241</td>
    </tr>
    <tr>
      <th>2014-05-07</th>
      <td> 20435</td>
      <td> 22012</td>
    </tr>
    <tr>
      <th>2014-05-08</th>
      <td> 20006</td>
      <td> 20266</td>
    </tr>
    <tr>
      <th>2014-05-09</th>
      <td> 20089</td>
      <td> 20308</td>
    </tr>
    <tr>
      <th>2014-05-10</th>
      <td> 22266</td>
      <td> 26210</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 2 columns</p>
</div>



### Aggregate into days by taking the median value of each day's worth of hourly observation


```python
df.resample('D', how='median')
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>german_army</th>
      <th>allied_army</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-05-06</th>
      <td> 23820</td>
      <td> 29733.0</td>
    </tr>
    <tr>
      <th>2014-05-07</th>
      <td> 25661</td>
      <td> 29292.0</td>
    </tr>
    <tr>
      <th>2014-05-08</th>
      <td> 25276</td>
      <td> 32969.0</td>
    </tr>
    <tr>
      <th>2014-05-09</th>
      <td> 24177</td>
      <td> 26887.5</td>
    </tr>
    <tr>
      <th>2014-05-10</th>
      <td> 27233</td>
      <td> 32542.0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 2 columns</p>
</div>



### Aggregate into days by taking the first value of each day's worth of hourly observation


```python
df.resample('D', how='first')
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>german_army</th>
      <th>allied_army</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-05-06</th>
      <td> 21331</td>
      <td> 39348</td>
    </tr>
    <tr>
      <th>2014-05-07</th>
      <td> 27290</td>
      <td> 36896</td>
    </tr>
    <tr>
      <th>2014-05-08</th>
      <td> 21352</td>
      <td> 38357</td>
    </tr>
    <tr>
      <th>2014-05-09</th>
      <td> 25561</td>
      <td> 21868</td>
    </tr>
    <tr>
      <th>2014-05-10</th>
      <td> 28359</td>
      <td> 39177</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 2 columns</p>
</div>



### Aggregate into days by taking the last value of each day's worth of hourly observation


```python
df.resample('D', how='last')
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>german_army</th>
      <th>allied_army</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-05-06</th>
      <td> 24976</td>
      <td> 29632</td>
    </tr>
    <tr>
      <th>2014-05-07</th>
      <td> 26162</td>
      <td> 30592</td>
    </tr>
    <tr>
      <th>2014-05-08</th>
      <td> 28828</td>
      <td> 36941</td>
    </tr>
    <tr>
      <th>2014-05-09</th>
      <td> 25573</td>
      <td> 24839</td>
    </tr>
    <tr>
      <th>2014-05-10</th>
      <td> 22266</td>
      <td> 35398</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 2 columns</p>
</div>



### Aggregate into days by taking the first, last, highest, and lowest value of each day's worth of hourly observation


```python
df.resample('D', how='ohlc')
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="4" halign="left">german_army</th>
      <th colspan="4" halign="left">allied_army</th>
    </tr>
    <tr>
      <th></th>
      <th>open</th>
      <th>high</th>
      <th>low</th>
      <th>close</th>
      <th>open</th>
      <th>high</th>
      <th>low</th>
      <th>close</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2014-05-06</th>
      <td> 21331</td>
      <td> 29557</td>
      <td> 20310</td>
      <td> 24976</td>
      <td> 39348</td>
      <td> 39348</td>
      <td> 20241</td>
      <td> 29632</td>
    </tr>
    <tr>
      <th>2014-05-07</th>
      <td> 27290</td>
      <td> 29998</td>
      <td> 20435</td>
      <td> 26162</td>
      <td> 36896</td>
      <td> 39686</td>
      <td> 22012</td>
      <td> 30592</td>
    </tr>
    <tr>
      <th>2014-05-08</th>
      <td> 21352</td>
      <td> 29253</td>
      <td> 20006</td>
      <td> 28828</td>
      <td> 38357</td>
      <td> 39996</td>
      <td> 20266</td>
      <td> 36941</td>
    </tr>
    <tr>
      <th>2014-05-09</th>
      <td> 25561</td>
      <td> 29792</td>
      <td> 20089</td>
      <td> 25573</td>
      <td> 21868</td>
      <td> 38827</td>
      <td> 20308</td>
      <td> 24839</td>
    </tr>
    <tr>
      <th>2014-05-10</th>
      <td> 28359</td>
      <td> 28359</td>
      <td> 22266</td>
      <td> 22266</td>
      <td> 39177</td>
      <td> 39177</td>
      <td> 26210</td>
      <td> 35398</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 8 columns</p>
</div>


