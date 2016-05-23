Title: Save A Matplotlib Plot As A Vector
Slug: matplotlib_save_a_plot_as_vector
Summary: Save A Matplotlib Plot As A Vector
Date: 2016-05-01 12:00
Category: Python
Tags: Data Visualization
Authors: Chris Albon



### Import Numpy and matplotlib.pyplot


```python
%matplotlib inline

import numpy as np
import matplotlib.pyplot as plt
```

### Create two new variables for mu and sigma


```python
mu, sigma = 100, 15
```

### Create some simulated data of 10000 values


```python
x = mu + sigma * np.random.randn(10000)
```

### Create a histogram of the simulated data.


```python
n, bins, patches = plt.hist(x, 50, normed=1, facecolor='g', alpha=0.75)
```


![png]({filename}/images/matplotlib_save_a_plot_as_vector/output_8_0.png)


### Set the x axis label.


```python
plt.xlabel('Smarts')
```




    <matplotlib.text.Text at 0x108709b90>




![png]({filename}/images/matplotlib_save_a_plot_as_vector/output_10_1.png)


### Set the y axis label.


```python
plt.ylabel('Probability')
```




    <matplotlib.text.Text at 0x108790890>




![png]({filename}/images/matplotlib_save_a_plot_as_vector/output_12_1.png)


### Set the plot title.


```python
plt.title('Histogram of IQ')
```




    <matplotlib.text.Text at 0x108937650>




![png]({filename}/images/matplotlib_save_a_plot_as_vector/output_14_1.png)


### Add some text in the corner.


```python
plt.text(60, .025, r'$\mu=100,\ \sigma=15$')
```




    <matplotlib.text.Text at 0x1089b9390>




![png]({filename}/images/matplotlib_save_a_plot_as_vector/output_16_1.png)


### Set the axes


```python
plt.axis([40, 160, 0, 0.03])
```




    [40, 160, 0, 0.03]




![png]({filename}/images/matplotlib_save_a_plot_as_vector/output_18_1.png)


### Save the plot as an EPS vector file.


```python
plt.savefig("example_plot.eps")
```


    <matplotlib.figure.Figure at 0x1089c0250>

