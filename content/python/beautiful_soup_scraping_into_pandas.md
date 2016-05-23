Title: Scraping And Parsing A Wikipedia List into Pandas
Slug: beautiful_soup_scraping_into_pandas
Summary: Scraping And Parsing A Wikipedia List into Pandas
Date: 2016-05-01 12:00
Category: Python
Tags: Web Scraping
Authors: Chris Albon



### Preliminaries


```python
# Import required modules
import requests
from bs4 import BeautifulSoup
import pandas as pd
```

### Create a beautiful soup object from the website


```python
# Create a variable with the URL to this tutorial
url = 'http://en.wikipedia.org/wiki/List_of_airship_accidents'

# Scrape the HTML at the url
r = requests.get(url)

# Turn the HTML into a Beautiful Soup object
soup = BeautifulSoup(r.text)
```

### Parse the html into a list


```python
# Create a list for the scraping results
disasters = []
```

The structure of the page is such that if we take all the *li* items **without** a tag, and then ignore the last three, we will have a clean list of all the disasters


```python
# Create a list elment for each li without a class (except for the last three)
# Then, for each row, append the text to disasters.
for row in soup.find_all('li', class_=False)[:-3]:
    disasters.append(row.text)
```

### Data wrangle the list into a dataframe


```python
# Create a dataframe from the list
df = pd.DataFrame(disasters, columns=['raw'])
```


```python
# Take everything before the ":" and call that the date variable
df['date'] = df['raw'].str.extract('(^[^_]+(?=:))')
```


```python
# Take everything after the ":" and call that the description variable
df['description'] = df['raw'].str.extract('\:(.*)')
```


```python
# Set the date variable to be time
df['date'] = pd.to_datetime(df['date'])
```


```python
# Set the date variable to be the dataFrame's index
df.index = df['date']
```


```python
# Drop the variables we no longer need
df = df.drop(['raw', 'date'], axis=1)
```

### View the results


```python
# View the top of the dataframe
df.head()
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;">
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>description</th>
    </tr>
    <tr>
      <th>date</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2 May 1902</th>
      <td>  Semi-rigid airship Pax explodes over Paris, k...</td>
    </tr>
    <tr>
      <th>13 October 1902</th>
      <td>  Separation of gondola from envelope over Pari...</td>
    </tr>
    <tr>
      <th>30 November 1907</th>
      <td>  Loss of the French Army's Patrie - no fatalit...</td>
    </tr>
    <tr>
      <th>23 May 1908</th>
      <td>  Morrell airship falls over Berkeley, Californ...</td>
    </tr>
    <tr>
      <th>4 August 1908</th>
      <td>  Zeppelin LZ 4 caught fire near Echterdingen a...</td>
    </tr>
  </tbody>
</table>
</div>
