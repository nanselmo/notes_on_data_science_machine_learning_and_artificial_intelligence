Title: 2D Density Plot
Slug: 2d-density-plot
Summary: 2D Density Plot
Date: 2016-05-01 12:00
Category: R Stats
Tags: Data Visualization
Authors: Chris Albon

Want to learn more? I recommend working through: [R for Data Science](http://amzn.to/2myxnhi), [R Cookbook](http://amzn.to/2lF6hkb), and [R Graphics Cookbook](http://amzn.to/2m0fcPL).

```R
# load the gcookbook package for the data
library(gcookbook)

# load the ggplot2 package
library(ggplot2)

# reset the graphing device
dev.off()

# create the ggplot2 data
p <- ggplot(faithful, aes(x = eruptions, y = waiting)) +
  # add a layer with the points
  geom_point() +
  # and a layer for the density heatmap with the alpha and the color determined by density (the .. refers to the fact that density is a variable that was created inside the ggplot() function)
  stat_density2d(aes(alpha=..density.., fill=..density..), geom="tile", contour=FALSE)
```




    null device
              1




```R
p
```









![png]({filename}/images/2d-density-plot_files/2d-density-plot_2_1.png)
