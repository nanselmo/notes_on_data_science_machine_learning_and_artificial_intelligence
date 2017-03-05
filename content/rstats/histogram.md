Title: Histogram
Slug: histogram
Summary: Histogram
Date: 2016-05-01 12:00
Category: R Stats
Tags: Data Visualization
Authors: Chris Albon

Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).


```R
# load the ggplot2 package
library(ggplot2)
```


```R
# hisotogram of the mpg variable from the mtcars dataset
ggplot(mtcars, aes(x=mpg)) + geom_histogram(binwidth=4)
```









![png]({filename}/images/histogram_files/histogram_2_1.png)
