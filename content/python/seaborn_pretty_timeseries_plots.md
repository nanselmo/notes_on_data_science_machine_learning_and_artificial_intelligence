Title: Make Pretty Time Series Plots With Seaborne
Slug: seaborn_pretty_timeseries_plots
Summary: Make Pretty Time Series Plots With Seaborne
Date: 2016-05-01 12:00
Category: Python
Tags: Data Visualization
Authors: Chris Albon



## Preliminaries


```python
import pandas as pd
%matplotlib inline
import matplotlib.pyplot as plt
import seaborn as sns
```


```python
data = {'date': [2001, 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010], 
        'deaths_regiment_1': [34, 43, 14, 15, 15, 14, 31, 25, 62, 41],
        'deaths_regiment_2': [52, 66, 78, 15, 15, 5, 25, 25, 86, 1],
        'deaths_regiment_3': [13, 73, 82, 58, 52, 87, 26, 5, 56, 75],
        'deaths_regiment_4': [44, 75, 26, 15, 15, 14, 54, 25, 24, 72],
        'deaths_regiment_5': [25, 24, 25, 15, 57, 68, 21, 27, 62, 5],
        'deaths_regiment_6': [84, 84, 26, 15, 15, 14, 26, 25, 62, 24],
        'deaths_regiment_7': [46, 57, 26, 15, 15, 14, 26, 25, 62, 41]}
df = pd.DataFrame(data, columns = ['date', 'battle_deaths', 'deaths_regiment_1', 'deaths_regiment_2',
                                   'deaths_regiment_3', 'deaths_regiment_4', 'deaths_regiment_5',
                                   'deaths_regiment_6', 'deaths_regiment_7'])
df = df.set_index(df.date)
```

## Set the color of a plot


```python
sns.tsplot([df.deaths_regiment_1, df.deaths_regiment_2, df.deaths_regiment_3, df.deaths_regiment_4,
            df.deaths_regiment_5, df.deaths_regiment_6, df.deaths_regiment_7])
```




    <matplotlib.axes._subplots.AxesSubplot at 0x104b225d0>




![png]({filename}/images/seaborn_pretty_timeseries_plots/output_5_1.png)



```python
custom_style = {'axes.axisbelow': True,
                'axes.edgecolor': '#FFFFFF',
                'axes.facecolor': '#F4F4F4',
                'axes.grid': False,
                'axes.labelcolor': '0',
                'axes.linewidth': 0,
                'font.family': ['sans-serif'],
                'font.sans-serif': ['Arial',
                  'Liberation Sans',
                  'Bitstream Vera Sans',
                  'sans-serif'],
                'grid.color': '0',
                'grid.linestyle': '-',
                'image.cmap': 'Greys',
                'legend.frameon': False,
                'legend.numpoints': 0,
                'legend.scatterpoints': 0,
                'lines.solid_capstyle': 'round',
                'text.color': '0',
                'xtick.color': '0',
                'xtick.direction': 'out',
                'xtick.major.size': '0',
                'xtick.minor.size': '0',
                'ytick.color': '0',
                'ytick.direction': 'out',
                'ytick.major.size': '0',
                'ytick.minor.size': '0'}

sns.set_context("notebook", font_scale=1.1)
sns.set_style(custom_style)

plt.subplot()
sns.tsplot([df.deaths_regiment_1, df.deaths_regiment_2, df.deaths_regiment_3, 
            df.deaths_regiment_4, df.deaths_regiment_5, df.deaths_regiment_6, 
            df.deaths_regiment_7], color="#34495e")
plt.title('Histogram of IQ')
plt.xlabel('Time')
plt.ylabel('Deaths')
plt.annotate('Battle of Two Bridges', xy=(4, 26), xytext=(5, 40),
             arrowprops=dict(facecolor='indianred', shrink=0.05, headwidth=20, 
                             frac=.2, width=7))
```




    <matplotlib.text.Annotation at 0x10a792450>




![png]({filename}/images/seaborn_pretty_timeseries_plots/output_6_1.png)

