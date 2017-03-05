Title: Finding the most common element
Slug: find-most-common-element
Summary: Finding the most common element
Date: 2016-05-01 12:00
Category: R Stats
Tags: Data Wrangling
Authors: Chris Albon


Original source: http://www.unc.edu/~jasperlm/Rsnippets.html

Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).
```R
# Create a list of wars
wars <- c("Spanish Civil War", "Spanish Civil War", "Spanish Civil War", "Spanish Civil War", "WWII", "WWII")
```


```R
# Create a function that finds the most common element in an object
most.common <- function(x) {
  count <- sapply(unique(x), function(i) sum(x==i, na.rm=TRUE))
  unique(x)[which(count==max(count))]
}
```


```R
# Run the function on the list of wars
most.common(wars)
```




    [1] "Spanish Civil War"
