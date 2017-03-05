Title: Difference Between Two Date-Times
Slug: difference-between-two-dates
Summary: Difference Between Two Date-Times
Date: 2016-05-01 12:00
Category: R Stats
Tags: Data Wrangling
Authors: Chris Albon


Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).

```R
# Create two dates
the_start_of_time <- as.Date("1970-01-01")
the_end_of_time <- as.Date("2012-12-21")
```


```R
# calculate the difference in the two dates
difftime(the_end_of_time, the_start_of_time, units = "auto")
```




    Time difference of 15695 days




```R
# calculate the difference in the two dates
difftime(the_end_of_time, the_start_of_time, units = "days")
```




    Time difference of 15695 days




```R
# calculate the difference in the two dates
difftime(the_end_of_time, the_start_of_time, units = "weeks")
```




    Time difference of 2242.143 weeks
