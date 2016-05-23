Title: Draw a histogram plot in ggplot
Slug: ggplot_histogram
Summary: Draw a histogram plot in ggplot
Date: 2016-05-01 12:00
Category: Python
Tags: Data Visualization
Authors: Chris Albon




```python
# Import required modules
from ggplot import *
%matplotlib inline
import pandas as pd
```


```python
# Create a dataset of Prussian Horsekick data data.
# This data presents the number of horsekick deaths per year in each corps
df = pd.DataFrame({
    "guard_corps": [0,2,2,1,0,0,1,1,0,3,0,2,1,0,0,1,0,1,0,1],
    "corps_1": [0,0,0,2,0,3,0,2,0,0,0,1,1,1,0,2,0,3,1,0],
    "corps_2": [0,0,0,2,0,2,0,0,1,1,0,0,2,1,1,0,0,2,0,0],
    "corps_3": [0,0,0,1,1,1,2,0,2,0,0,0,1,0,1,2,1,0,0,0],
    "corps_4": [0,1,0,1,1,1,1,0,0,0,0,1,0,0,0,0,1,1,0,0],
    "corps_5": [0,0,0,0,2,1,0,0,1,0,0,1,0,1,1,1,1,1,1,0],
    "corps_6": [0,0,1,0,2,0,0,1,2,0,1,1,3,1,1,1,0,3,0,0],
    "corps_7": [1,0,1,0,0,0,1,0,1,1,0,0,2,0,0,2,1,0,2,0],
    "corps_8": [1,0,0,0,1,0,0,1,0,0,0,0,1,0,0,0,1,1,0,1],
    "corps_9": [0,0,0,0,0,2,1,1,1,0,2,1,1,0,1,2,0,1,0,0],
    "corps_10": [0,0,1,1,0,1,0,2,0,2,0,0,0,0,2,1,3,0,1,1],
    "corps_11": [0,0,0,0,2,4,0,1,3,0,1,1,1,1,2,1,3,1,3,1],
    "corps_14": [ 1,1,2,1,1,3,0,4,0,1,0,3,2,1,0,2,1,1,0,0],
    "corps_15": [0,1,0,0,0,0,0,1,0,1,1,0,0,0,2,2,0,0,0,0]
})
```


```python
# Create a histogram plot of the number of each value in corps_14
ggplot(aes(x='corps_14'), data=df) + \
    geom_histogram(binwidth=1)
```


![png]({filename}/images/ggplot_histogram/output_3_0.png)





    <ggplot: (281307829)>


