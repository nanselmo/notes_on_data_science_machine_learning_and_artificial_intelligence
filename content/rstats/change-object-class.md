Title: Change The Class Of An Object
Slug: change-object-class
Summary: Change The Class Of An Object
Date: 2016-05-01 12:00
Category: R Stats
Tags: Basics
Authors: Chris Albon

Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).

Changing the class of an object is called "casting".


```R
# Create a character string object
number.of.casualties <- "929040"
```


```R
# Convert it into a numeric object
number.of.casualties <- as.numeric(number.of.casualties)
```
