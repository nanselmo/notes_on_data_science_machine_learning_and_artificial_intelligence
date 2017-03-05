Title: Datasets
Slug: datasets
Summary: Datasets
Date: 2016-05-01 12:00
Category: R Stats
Tags: Basics
Authors: Chris Albon

Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).


```R
# view built-in datasets
data()
```


```R
# view all installed datasets from all installed packages
data(package = .packages(TRUE))
```

    Warning message:
    In data(package = .packages(TRUE)): datasets have been moved from package 'base' to package 'datasets'Warning message:
    In data(package = .packages(TRUE)): datasets have been moved from package 'stats' to package 'datasets'









```R
# load a dataset "votes.repub" from the installed package "cluster"
data("votes.repub", package = "cluster")
```
