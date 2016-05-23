Title: Load Excel Spreadsheet As Pandas Dataframe
Slug: pandas_dataframe_load_xls
Summary: Load Excel Spreadsheet As Pandas Dataframe
Date: 2016-05-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon




```python
# import modules
import pandas as pd
```


```python
# Import the excel file and call it xls_file
xls_file = pd.ExcelFile('/Users/chrisralbon/Dropbox (Personal)/Public/example.xls')
xls_file
```




    <pandas.io.excel.ExcelFile at 0x10742f210>




```python
# View the excel file's sheet names
xls_file.sheet_names
```




    ['Sheet1', 'Sheet2']




```python
# Load the xls file's Sheet1 as a dataframe
df = xls_file.parse('Sheet1')
df
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>FirstName</th>
      <th>LastName</th>
      <th>Location</th>
      <th>Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td> Jason</td>
      <td> Miller</td>
      <td> USA</td>
      <td> 43</td>
    </tr>
    <tr>
      <th>1</th>
      <td>  Bill</td>
      <td>  Macoi</td>
      <td> USA</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>2</th>
      <td>  Jane</td>
      <td>   Modi</td>
      <td>  UK</td>
      <td> 25</td>
    </tr>
    <tr>
      <th>3</th>
      <td>  Sara</td>
      <td>   Mosi</td>
      <td>  UK</td>
      <td> 62</td>
    </tr>
  </tbody>
</table>
<p>4 rows × 4 columns</p>
</div>


