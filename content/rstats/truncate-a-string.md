Title: Truncate A String
Slug: truncate-a-string
Summary: Truncate A String
Date: 2016-05-01 12:00
Category: R Stats
Tags: Data Wrangling
Authors: Chris Albon

Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).

Source: http://www.r-bloggers.com/truncate-by-delimiter-in-r/


```R
# create some simulated data
patients <- data.frame(
  uid = 1:3,
  fullname = c("Smith/John", "Jackson/Smith", "Joel/Billy"))
```


```R
patients$lastname <- sub("/.*", "", patients$fullname); patients$lastname
```




    [1] "Smith"   "Jackson" "Joel"   
