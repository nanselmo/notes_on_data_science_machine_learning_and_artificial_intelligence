Title: Kolmogorov Smirnov Test
Slug: kolmogorov_smirnov_test
Summary: Kolmogorov Smirnov Test
Date: 2016-12-01 12:00
Category: Python
Tags: Other
Authors: Chris Albon




```python
# Import required packages
from scipy import stats
import scipy as sp
import numpy as np
import math
import matplotlib.pyplot as plt
%matplotlib inline
```


```python
# Create x, which is uniformly distributed
x = np.random.uniform(size=1000)

# Plot x to double check its distribution
plt.hist(x)
plt.show()
```


![png]({filename}/images/kolmogorov_smirnov_test/output_2_0.png)



```python
# Create y, which is NOT uniformly distributed
y = x**4

# Plot y to double check its distribution
plt.hist(y)
plt.show()
```


![png]({filename}/images/kolmogorov_smirnov_test/output_3_0.png)



```python
# Run kstest on x. We want the second returned value to be 
# not statistically significant, meaning that both come from 
# the same distribution.
stats.kstest(x, 'uniform', args=(min(x),max(x)))
```




    (0.043685470092267642, 0.042698030459771275)




```python
# Run kstest on y. We want the second returned value to be 
# statistically significant, meaning that likely do not both 
# come from the same distribution.
stats.kstest(y, 'uniform', args=(min(y),max(y)))
```




    (0.48969825580402526, 0.0)


