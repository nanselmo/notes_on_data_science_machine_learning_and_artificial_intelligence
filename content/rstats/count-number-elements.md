Title: Count The Number Of Times X Appears In A Vector
Slug: count-number-elements
Summary: Count The Number Of Times X Appears In A Vector
Date: 2016-05-01 12:00
Category: R Stats
Tags: Basics
Authors: Chris Albon


Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).

```R
# create a vector of simulated data
numbers <- c(4,23,4,23,5,43,54,56,657,67,67,435,453,435,324,34,456,56,567,65,34,435)
```


```R
# create an object that is our x
x <- 67
```


```R
# the length of the subset of the variable numbers where numbers equals x
length(subset(numbers, numbers == x ))
```




    [1] 2
