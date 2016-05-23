Title: Test Script
Slug: testing_the_stack
Summary: Test Script
Date: 2016-05-01 12:00
Category: Python
Tags: Other
Authors: Chris Albon



Checks the right environment is being used and one of the data science modules is installed

### Import the modules


```python
import sys
import IPython
```

### Print the path to the Python environment.


```python
print(sys.executable)
print(sys.version)
```

    /Users/chrisralbon/anaconda/bin/python
    3.4.3 |Anaconda 2.3.0 (x86_64)| (default, Mar  6 2015, 12:07:41) 
    [GCC 4.2.1 (Apple Inc. build 5577)]


### Check which version of iPython is being used.


```python
IPython.__version__
```




    '4.0.0'



### Run a quick test to see if numpy module is installed.


```python
import numpy as np
arr = np.arange(100)
arr
```




    array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16,
           17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33,
           34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50,
           51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67,
           68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84,
           85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99])



### Run a quick test to see if pandas module is installed.


```python
import pandas as pd
```


```python
df = pd.DataFrame(np.random.randn(8, 3), 
                  index=pd.date_range('1/1/2000', periods=8), 
                  columns=['A', 'B', 'C'])
df
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2000-01-01</th>
      <td>-0.089910</td>
      <td>-0.913436</td>
      <td>-2.641454</td>
    </tr>
    <tr>
      <th>2000-01-02</th>
      <td>-0.158907</td>
      <td>1.945974</td>
      <td>0.503885</td>
    </tr>
    <tr>
      <th>2000-01-03</th>
      <td>-1.336161</td>
      <td>-0.064529</td>
      <td>0.356160</td>
    </tr>
    <tr>
      <th>2000-01-04</th>
      <td>0.165625</td>
      <td>1.527331</td>
      <td>-1.659235</td>
    </tr>
    <tr>
      <th>2000-01-05</th>
      <td>0.004940</td>
      <td>0.012336</td>
      <td>-1.767828</td>
    </tr>
    <tr>
      <th>2000-01-06</th>
      <td>0.621349</td>
      <td>1.869468</td>
      <td>0.889847</td>
    </tr>
    <tr>
      <th>2000-01-07</th>
      <td>0.670501</td>
      <td>0.263122</td>
      <td>0.693141</td>
    </tr>
    <tr>
      <th>2000-01-08</th>
      <td>-0.102067</td>
      <td>-0.010609</td>
      <td>-0.820762</td>
    </tr>
  </tbody>
</table>
</div>



### View the first 4 rows.


```python
df[0:4]
```




<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2000-01-01</th>
      <td>-0.089910</td>
      <td>-0.913436</td>
      <td>-2.641454</td>
    </tr>
    <tr>
      <th>2000-01-02</th>
      <td>-0.158907</td>
      <td>1.945974</td>
      <td>0.503885</td>
    </tr>
    <tr>
      <th>2000-01-03</th>
      <td>-1.336161</td>
      <td>-0.064529</td>
      <td>0.356160</td>
    </tr>
    <tr>
      <th>2000-01-04</th>
      <td>0.165625</td>
      <td>1.527331</td>
      <td>-1.659235</td>
    </tr>
  </tbody>
</table>
</div>


