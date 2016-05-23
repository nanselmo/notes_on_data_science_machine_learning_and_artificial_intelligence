Title: Map Your Google Location History
Slug: matplotlib_map_your_google_data
Summary: Map Your Google Location History
Date: 2016-05-01 12:00
Category: Python
Tags: Data Visualization
Authors: Chris Albon



## Step 1: Download your Google Location History

Google makes this process very easy. Go here to [download your location history data](https://www.google.com/settings/takeout) and unzip it.

## Step 2: Run this script

### Preliminaries


```python
# Import pandas
import pandas as pd

# Import matplotlib and Basemap
import matplotlib.pyplot as plt
from mpl_toolkits.basemap import Basemap

# Set iPython to display visualization inline
%matplotlib inline
```

### Read in the location history json

Simply change the string to point to where you unzipped your location history json file


```python
# Create a dataframe from the json file in the filepath
raw = pd.io.json.read_json('/Users/chrisralbon/Downloads/Location History/LocationHistory.json')
```

### Let's take a look at some of the data


```python
# View the last five rows of the dataframe
raw.tail()
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>locations</th>
      <th>somePointsTruncated</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>369608</th>
      <td> {'timestampMs': '1360251651345', 'longitudeE7'...</td>
      <td> True</td>
    </tr>
    <tr>
      <th>369609</th>
      <td> {'timestampMs': '1360251591250', 'longitudeE7'...</td>
      <td> True</td>
    </tr>
    <tr>
      <th>369610</th>
      <td> {'timestampMs': '1360251521053', 'longitudeE7'...</td>
      <td> True</td>
    </tr>
    <tr>
      <th>369611</th>
      <td> {'timestampMs': '1360249108976', 'longitudeE7'...</td>
      <td> True</td>
    </tr>
    <tr>
      <th>369612</th>
      <td> {'timestampMs': '1360242137146', 'longitudeE7'...</td>
      <td> True</td>
    </tr>
  </tbody>
</table>
</div>



### Expand the locations object into it's own dataframe


```python
# Expand the locations column into a dataframe
# This lets us move down one level in the json structure
df = raw['locations'].apply(pd.Series)
```

### Take a peak at the data again


```python
# View the last five rows of the dataframe
df.tail()
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>accuracy</th>
      <th>activitys</th>
      <th>altitude</th>
      <th>heading</th>
      <th>latitudeE7</th>
      <th>longitudeE7</th>
      <th>timestampMs</th>
      <th>velocity</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>369608</th>
      <td>   57</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> 388976217</td>
      <td>-770434474</td>
      <td> 1360251651345</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>369609</th>
      <td>   52</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> 388974040</td>
      <td>-770433938</td>
      <td> 1360251591250</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>369610</th>
      <td>   34</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> 388974020</td>
      <td>-770432626</td>
      <td> 1360251521053</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>369611</th>
      <td>   50</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> 388974020</td>
      <td>-770432626</td>
      <td> 1360249108976</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>369612</th>
      <td> 1064</td>
      <td> NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td> 389467326</td>
      <td>-769333633</td>
      <td> 1360242137146</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>



### Wrangle the data


```python
# Create a list from the latitude column, multiplied by -E7
df['latitude'] = df['latitudeE7'] * 0.0000001

# Create a list from the longitude column, multiplied by -E7
df['longitude'] = df['longitudeE7'] * 0.0000001
```

### Map the data using basemap


```python
# Create a figure of size (i.e. pretty big)
fig = plt.figure(figsize=(20,10))

# Create a map, using the Gall–Peters projection, 
map = Basemap(projection='gall', 
              # with low resolution,
              resolution = 'l', 
              # And threshold 100000
              area_thresh = 100000.0,
              # Centered at 0,0 (i.e null island)
              lat_0=0, lon_0=0)

# Draw the coastlines on the map
map.drawcoastlines()

# Draw country borders on the map
map.drawcountries()

# Fill the land with grey
map.fillcontinents(color = '#888888')

# Draw the map boundaries
map.drawmapboundary(fill_color='#f4f4f4')

# Define our longitude and latitude points
x,y = map(df['longitude'].values, df['latitude'].values)

# Plot them using round markers of size 6
map.plot(x, y, 'ro', markersize=6)
 
# Show the map
plt.show()
```


![png]({filename}/images/matplotlib_map_your_google_data/output_16_0.png)

