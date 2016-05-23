Title: Two Way Frequency Table
Slug: 2-way-frequency-table
Summary: Two Way Frequency Table
Date: 2016-05-01 12:00
Category: R Stats
Tags: Data Visualization
Authors: Chris Albon



Original source: http://www.statmethods.net/stats/frequencies.html


```R
A <- c("yes", "no","yes", "no","yes", "no","yes", "no")
B <- c("male", "female","female", "male","male", "male","male", "male")
```


```R
mytable <- table(A,B) # A will be rows, B will be columns
mytable # print table
```




         B
    A     female male
      no       1    3
      yes      1    3




```R
margin.table(mytable, 1) # A frequencies (summed over B)
margin.table(mytable, 2) # B frequencies (summed over A)
```




    A
     no yes
      4   4






    B
    female   male
         2      6




```R
prop.table(mytable) # cell percentages
prop.table(mytable, 1) # row percentages
prop.table(mytable, 2) # column percentages
```




         B
    A     female  male
      no   0.125 0.375
      yes  0.125 0.375






         B
    A     female male
      no    0.25 0.75
      yes   0.25 0.75






         B
    A     female male
      no     0.5  0.5
      yes    0.5  0.5
