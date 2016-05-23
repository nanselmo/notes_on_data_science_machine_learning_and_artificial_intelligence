Title: Adding Levels To A Factor (i.e. adding Categories To A Nominal Variable)
Slug: add-levels-to-factors
Summary: Adding Levels To A Factor (i.e. adding Categories To A Nominal Variable)
Date: 2016-05-01 12:00
Category: R Stats
Tags: Basics
Authors: Chris Albon



A Factor object is used to unordered categories, that is categories where each one is different but considered equal (e.g. types of fruit, names, gender, countries, etc.) One common problem people have with factors is trying to add a level (i.e. add a category) to a factor. The reason is that in order to manipulate factors, you have to manipulate it's levels, not the names of each category.


```R
# create simulated distract name data
district <- c("NORTH", "NORTHWEST", "CENTRAL", "SOUTH", "SOUTHWEST", "EAST")

# remake district categories with the combination of district categories and a new SOUTH CENTRAL category
levels(district) <- c(district, "SOUTH CENTRAL")
```


```R
levels(district)
```




    [1] "NORTH"         "NORTHWEST"     "CENTRAL"       "SOUTH"        
    [5] "SOUTHWEST"     "EAST"          "SOUTH CENTRAL"
