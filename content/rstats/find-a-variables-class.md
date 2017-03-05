Title: Classes
Slug: find-a-variables-class
Summary: Classes
Date: 2016-05-01 12:00
Category: R Stats
Tags: Data Wrangling
Authors: Chris Albon


Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).

Classes tell you what type a paticular variable is, whether numeric or logistic.

Use the class() function to find out a variable's class


```R
# Create a variable called "crime", containing numeric data
crime <- c(1,2,4,5)
```


```R
# find the class of the variable "crime"
class(crime)
```




    [1] "numeric"
