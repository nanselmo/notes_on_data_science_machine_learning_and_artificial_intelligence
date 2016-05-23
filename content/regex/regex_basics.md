Title: Regex Basics
Slug: regex_basics
Summary: Regex Basics
Date: 2016-05-01 12:00
Category: Regex
Tags: Basics
Authors: Chris Albon



## Preliminaries


```python
# Load regex package
import re
```

## Create some text


```python
# Create a variable containing a text string
text = 'We have reports of 9 men in the field. '
```

## Apply regex


```python
# Find any ISBN-10 or ISBN-13 number
re.findall(r'(\b[A-Z]+\b)(?=.*(?=\b[a-z]+\b)(?i)\1)', text)
```




    ['the', 'lords', 'of', 'Winterfell']


