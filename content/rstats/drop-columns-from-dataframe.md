Title: Drop Columns From Dataframe
Slug: drop-columns-from-dataframe
Summary: Drop Columns From Dataframe
Date: 2016-05-01 12:00
Category: R Stats
Tags: Data Wrangling
Authors: Chris Albon


Original Source: http://stackoverflow.com/questions/4605206/drop-columns-r-data-frame

Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).

```R
# create a dataframe with three columns
df <- data.frame(x = runif(100), y = runif(100), z = runif(100))
```


```R
# drop columns y and z
df <- subset(df, select = -c(y, z) )
```


```R
# only keep column x (thus dropping y and z)
df <- subset(df, select = c(x))
```
