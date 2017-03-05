Title: apropos functions finds objects and functions
Slug: find-objects-variables-functions
Summary: apropos functions finds objects and functions
Date: 2016-05-01 12:00
Category: R Stats
Tags: Data Wrangling
Authors: Chris Albon


Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).

```R
# Create a vector with various kitten names
kitten.names <- c("Stacy", "McKiddleton", "Cat Number Two")
```


```R
# Find any object and function with "kitten" in the name
apropos("kitten")
```




    character(0)
