Title: Sample Rows Of A Dataframe In Pandas
Slug: pandas_sample_dataframe
Summary: Sample Rows Of A Dataframe In Pandas
Date: 2016-05-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon



### Import required modules


```python
import pandas as pd
import numpy as np
```

### Create a dataframe of test scores


```python
df = pd.DataFrame(np.random.randn(100, 4), columns=['test1_score', 'test2_score' ,'test3_score' ,'test4_score'])
```

### View the top five rows


```python
df.head()
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>test1_score</th>
      <th>test2_score</th>
      <th>test3_score</th>
      <th>test4_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>-0.562832</td>
      <td> 0.285719</td>
      <td> 0.937775</td>
      <td>-1.638723</td>
    </tr>
    <tr>
      <th>1</th>
      <td> 0.298900</td>
      <td>-1.215272</td>
      <td> 1.461132</td>
      <td> 0.866500</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-1.049831</td>
      <td> 1.767881</td>
      <td> 0.221468</td>
      <td>-1.165039</td>
    </tr>
    <tr>
      <th>3</th>
      <td> 1.360927</td>
      <td> 0.846616</td>
      <td>-1.559061</td>
      <td>-1.340281</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-0.022707</td>
      <td> 0.946102</td>
      <td> 0.232905</td>
      <td> 0.615826</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 4 columns</p>
</div>



### Length of the dataframe


```python
print(len(df))
```

    100


### Randomly choose 10 rows


```python
rows = np.random.choice(df.index.values, 10)
```

### Convert it into a dataframe


```python
sampled_df = df.ix[rows]
```

### View the dataframe


```python
sampled_df
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>test1_score</th>
      <th>test2_score</th>
      <th>test3_score</th>
      <th>test4_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>61</th>
      <td> 0.350195</td>
      <td>-1.199999</td>
      <td>-0.277451</td>
      <td>-1.286770</td>
    </tr>
    <tr>
      <th>46</th>
      <td>-0.310364</td>
      <td> 1.086771</td>
      <td>-0.521381</td>
      <td> 0.607132</td>
    </tr>
    <tr>
      <th>78</th>
      <td>-0.215014</td>
      <td> 0.464960</td>
      <td>-0.369023</td>
      <td>-2.332646</td>
    </tr>
    <tr>
      <th>9 </th>
      <td>-1.281638</td>
      <td>-0.268482</td>
      <td>-0.103900</td>
      <td> 1.559594</td>
    </tr>
    <tr>
      <th>78</th>
      <td>-0.215014</td>
      <td> 0.464960</td>
      <td>-0.369023</td>
      <td>-2.332646</td>
    </tr>
    <tr>
      <th>48</th>
      <td> 0.239393</td>
      <td>-0.090481</td>
      <td> 2.453789</td>
      <td>-0.126449</td>
    </tr>
    <tr>
      <th>68</th>
      <td>-1.078161</td>
      <td>-0.712167</td>
      <td> 0.303397</td>
      <td> 0.444029</td>
    </tr>
    <tr>
      <th>68</th>
      <td>-1.078161</td>
      <td>-0.712167</td>
      <td> 0.303397</td>
      <td> 0.444029</td>
    </tr>
    <tr>
      <th>51</th>
      <td> 0.087971</td>
      <td> 0.397842</td>
      <td>-0.086190</td>
      <td>-0.903375</td>
    </tr>
    <tr>
      <th>80</th>
      <td>-0.875859</td>
      <td>-0.873104</td>
      <td> 2.316806</td>
      <td> 0.518988</td>
    </tr>
  </tbody>
</table>
<p>10 rows × 4 columns</p>
</div>


