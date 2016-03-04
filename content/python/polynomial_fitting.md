Title: Polynomial Fitting
Slug: polynomial_fitting
Summary: Polynomial Fitting
Date: 2016-12-01 12:00
Category: Python
Tags: Other
Authors: Chris Albon




```python
import scipy.interpolate as sp

%pylab inline
```

    Populating the interactive namespace from numpy and matplotlib


### 50 points of sin(x) in [0 10]


```python
xx = numpy.linspace(0, 10, 50)
yy = numpy.sin(xx)
```

### 10 sample of sin(x) in [0 10]


```python
x = numpy.linspace(0, 10, 10)
y = numpy.sin(x)
```

### interpolation


```python
fl = sp.interp1d(x, y,kind='linear')
fc = sp.interp1d(x, y,kind='cubic')
```

### fl and fc are the interpolating functions
- defined in the interval [0 10]
- fl uses linear interpolation
- and fc uses cubic interpolation


```python
xnew = numpy.linspace(0, 10, 50)
pylab.subplot(211)
```




    <matplotlib.axes.AxesSubplot at 0x10a3e1090>




![png]({filename}/images/polynomial_fitting/output_9_1.png)


### the real sin(x) function plot


```python
pylab.plot(xx, yy)
pylab.legend(['sin(x)'], loc='best')
pylab.subplot(212)
```




    <matplotlib.axes.AxesSubplot at 0x109628450>




![png]({filename}/images/polynomial_fitting/output_11_1.png)


### the interpolation


```python
pylab.plot(x, y, 'o', xnew, fl(xnew), xnew, fc(xnew))
pylab.legend(['sample', 'linear', 'cubic'], loc='lower left')
```




    <matplotlib.legend.Legend at 0x10a34cc10>




![png]({filename}/images/polynomial_fitting/output_13_1.png)

