Title: Parse JSON File
Slug: json_parse_file
Summary: Parse JSON File
Date: 2016-05-01 12:00
Category: Python
Tags: Data Wrangling
Authors: Chris Albon



## Preliminaries


```python
import json
import pandas as pd
import requests
```

## Get data


```python
# Pull down some simple json data
r = requests.get('http://api.zippopotam.us/us/ma/belmont')

# Convert it into a python object
data = r.json()
```


```python
# View the data
data
```




    {'state abbreviation': 'MA',
     'place name': 'Belmont',
     'country abbreviation': 'US',
     'state': 'Massachusetts',
     'places': [{'longitude': '-71.4594',
       'latitude': '42.4464',
       'place name': 'Belmont',
       'post code': '02178'},
      {'longitude': '-71.2044',
       'latitude': '42.4128',
       'place name': 'Belmont',
       'post code': '02478'}],
     'country': 'United States'}



## Parse data


```python
# One level deep
data['places']
```




    [{'longitude': '-71.4594',
      'latitude': '42.4464',
      'place name': 'Belmont',
      'post code': '02178'},
     {'longitude': '-71.2044',
      'latitude': '42.4128',
      'place name': 'Belmont',
      'post code': '02478'}]




```python
# One level deep, second element
data['places'][1]
```




    {'longitude': '-71.2044',
     'latitude': '42.4128',
     'place name': 'Belmont',
     'post code': '02478'}




```python
# One level down, then second item, then it's longitude object
data['places'][1]['longitude']
```




    '-71.2044'



## Create a for loop to extract all lat/long coordinates


```python
# For each element, i, in data.places,
for i in data['places']:
    # print the latitude element and the longitude element
    print(i['latitude'], i['longitude'])
```

    42.4464 -71.4594
    42.4128 -71.2044


## Same as above, but as a function


```python
# Create a function that
def extract_latlong(json):
    # For each element, i, in data.places,
    for i in data['places']:
        # print the latitude element and the longitude element
        print(i['latitude'], i['longitude'])
```


```python
# Run the function
extract_latlong(data)
```

    42.4464 -71.4594
    42.4128 -71.2044

