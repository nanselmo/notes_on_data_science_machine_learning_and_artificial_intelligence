Title: Nested For Loops Using List Comprehension   
Slug: nested_for_loops_using_list_comprehension   
Summary: Nested For Loops Using List Comprehension   
Date: 2016-11-01 12:00  
Category: Python  
Tags: Basic  
Authors: Chris Albon  

Want to learn more? I recommend these Python books: [Python for Data Analysis](http://amzn.to/2ljV9wY), [Python Data Science Handbook](http://amzn.to/2m0mgMB), and [Introduction to Machine Learning with Python](http://amzn.to/2mjYiwK).

```python
# Create two lists
squads = ["1st Squad", '2nd Squad', '3rd Squad']
regiments = ["51st Regiment", '15th Regiment', '12th Regiment']
```


```python
# Create a tuple for each regiment in regiments, for each squad in sqauds
[(regiment, squad) for regiment in regiments for squad in squads ]
```




    [('51st Regiment', '1st Squad'),
     ('51st Regiment', '2nd Squad'),
     ('51st Regiment', '3rd Squad'),
     ('15th Regiment', '1st Squad'),
     ('15th Regiment', '2nd Squad'),
     ('15th Regiment', '3rd Squad'),
     ('12th Regiment', '1st Squad'),
     ('12th Regiment', '2nd Squad'),
     ('12th Regiment', '3rd Squad')]
