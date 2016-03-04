Title: View An Image In Jupyter Notebook
Slug: ipython_display_image
Summary: View An Image In Jupyter Notebook
Date: 2010-12-03 10:20
Category: Jupyter
Tags:
Authors: Chris Albon

## Display an image


```python
# Load the ipython display and image module
from IPython.display import Image
from IPython.display import display
```


```python
# display this image
display(Image(url='http://history.nasa.gov/ap11ann/kippsphotos/5903.jpg'))
```


<img src="http://history.nasa.gov/ap11ann/kippsphotos/5903.jpg"/>


## Display an svg


```python
# Load the svg module
from IPython.display import SVG

# Display an svg
SVG(url='http://upload.wikimedia.org/wikipedia/en/a/a4/Flag_of_the_United_States.svg')
```




![svg]({filename}/images/ipython_display_image/output_5_0.svg)
