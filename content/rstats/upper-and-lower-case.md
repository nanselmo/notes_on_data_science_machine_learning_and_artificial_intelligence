Title: Changing Uppercase And Lowercase
Slug: upper-and-lower-case
Summary: Changing Uppercase And Lowercase
Date: 2016-05-01 12:00
Category: R Stats
Tags: Basics
Authors: Chris Albon


Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).

```R
# create a character vector
text <- c("DSFGSsdffdsDSF", "DdsFDSFsdfSsdf", "DDDDDDDD", "kkkkkkkk")
```


```R
# convert to upper case
toupper(text)
```




    [1] "DSFGSSDFFDSDSF" "DDSFDSFSDFSSDF" "DDDDDDDD"       "KKKKKKKK"      




```R
# convert to all lower case
tolower(text)
```




    [1] "dsfgssdffdsdsf" "ddsfdsfsdfssdf" "dddddddd"       "kkkkkkkk"      
