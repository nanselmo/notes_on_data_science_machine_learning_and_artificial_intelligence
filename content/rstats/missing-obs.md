Title: Removing Missing Observations
Slug: missing-obs
Summary: Removing Missing Observations
Date: 2016-05-01 12:00
Category: R Stats
Tags: Data Wrangling
Authors: Chris Albon

Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).


```R
# Create some data with missing observations
ages <- c(3, 4, 9, NA, 93, 2, NA, NA, 2, 0, 2, 9)
```


```R
# Create a new variable that is a subset that doesn't include the missing observations
ages.no.na <- subset(ages, !is.na(ages))
```


```R
ages.no.na
```




    [1]  3  4  9 93  2  2  0  2  9
