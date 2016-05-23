Title: Load Jupyter Notebook In Non-Default Browser
Date: 2016-05-01 12:00
Category: Command Line
Tags:
Slug: open_ipython_nb_in_nondefault_browser
Authors: Chris Albon
Summary: List All Files And Folders In A Directory

The one part of Jupyter Notebooks that I don't like is not having a dedicated IDE for it. As an effective workaround, I started using Firefox as my general use browser and Chrome as my Jupyter Notebook "IDE".

However, by default Jupyter Notebooks loads the default browser (which in my is Firefox). The following bash script loads my Python 3 environment and then opens Jupyter Notebook in Chrome.

Note: I have commented out all the commands so it doesn't run while in Jupyter.


```python
%%bash

# Set the bash hashbang
# #!/bin/bash

# Activate my Python 3 environment
# source activate py3k

# Open IPython Notebook using Chrome
# BROWSER=/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome ipython notebook
```
