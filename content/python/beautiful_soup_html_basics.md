Title: Beautiful Soup Basic HTML Scraping
Slug: beautiful_soup_html_basics
Summary: Beautiful Soup Basic HTML Scraping
Date: 2016-05-01 12:00
Category: Python
Tags: Web Scraping
Authors: Chris Albon



### Import the modules


```python
# Import required modules
import requests
from bs4 import BeautifulSoup
```

### Scrap the html and turn into a beautiful soup object


```python
# Create a variable with the url
url = 'http://chrisralbon.com'

# Use requests to get the contents
r = requests.get(url)

# Get the text of the contents
html_content = r.text

# Convert the html content into a beautiful soup object
soup = BeautifulSoup(html_content)
```

### Select the website's title


```python
# View the title tag of the soup object
soup.title
```




    <title>Chris R. Albon</title>



### Website title's tag


```python
# View the name of the title
soup.title.name
```




    'title'



### Website title tag's string


```python
# View the string within the title tag
soup.title.string
```




    'Chris R. Albon'



### First paragraph tag


```python
# view the paragraph tag of the soup
soup.p
```




    <p class="site-description">Data for social good.</p>



### The parent of the title tag


```python
soup.title.parent.name
```




    'head'



### The class of the first paragraph tag


```python
soup.p['class']
```




    ['site-description']



### The first link tag


```python
soup.a
```




    <a class="logo" href="http://www.chrisralbon.com/about-chris-albon/"><img alt="Blog Logo" src="/content/images/2014/Feb/chrisalbon_radial-16.png"/></a>



### Find all the link tags


```python
soup.find_all('a')
```




    [<a class="logo" href="http://www.chrisralbon.com/about-chris-albon/"><img alt="Blog Logo" src="/content/images/2014/Feb/chrisalbon_radial-16.png"/></a>,
     <a href="http://www.chrisralbon.com">Chris R. Albon</a>,
     <a href="/conflict-health/">Conflict Health Has Shut Down</a>,
     <a href="/about-chris-albon/">About Chris Albon</a>,
     <a href="http://www.chrisralbon.com/about-chris-albon/">About</a>,
     <a href="https://twitter.com/chrisalbon">Twitter</a>,
     <a href="https://github.com/chrisalbon">GitHub</a>,
     <a href="https://pinboard.in/u:chrisalbon">Pinboard</a>]



### Get all the text on the page


```python
soup.get_text()
```




    '\n\n\n\nChris R. Albon\n\n\n\n\n\n\n\n\n\r\n\t\tvar infinite_conf = {"button_text":"Older posts","no_more_post":"No More Post","enable_infinite":"1"};\r\n\t\t\n\n\n\n\n\n\n\n\n\n\nChris R. Albon\n\nData for social good.\n\n\n\n\n\n\n\nFeb 16, 2014\n\nConflict Health Has Shut Down\n\n In 2008, I launched the blog Conflict Health to investigate and defend the role of health workers during political violence and armed conflicts. Four years later, I had written almost 500 posts on Conflict Health…\n\n\nFeb 14, 2014\n\nAbout Chris Albon\n\nShort version: I use data for social good. I also write about it. Longer version: I am the Director of a new crisis data project at Ushahidi, leading our work around the use of data…\n\n\n\nPage 1 of 1\n\n\n\n\n\n\nAbout | Twitter | GitHub | Pinboard\n\n\n\n\n\n\n\n\n'



### The string inside the first paragraph tag


```python
soup.p.string
```




    'Data for social good.'



### Find all the h2 tags


```python
soup.find_all('h2')
```




    [<h2 class="entry-title">
     <a href="/conflict-health/">Conflict Health Has Shut Down</a>
     </h2>, <h2 class="entry-title">
     <a href="/about-chris-albon/">About Chris Albon</a>
     </h2>]



### Find all the links on the page


```python
soup.find_all('a')
```




    [<a class="logo" href="http://www.chrisralbon.com/about-chris-albon/"><img alt="Blog Logo" src="/content/images/2014/Feb/chrisalbon_radial-16.png"/></a>,
     <a href="http://www.chrisralbon.com">Chris R. Albon</a>,
     <a href="/conflict-health/">Conflict Health Has Shut Down</a>,
     <a href="/about-chris-albon/">About Chris Albon</a>,
     <a href="http://www.chrisralbon.com/about-chris-albon/">About</a>,
     <a href="https://twitter.com/chrisalbon">Twitter</a>,
     <a href="https://github.com/chrisalbon">GitHub</a>,
     <a href="https://pinboard.in/u:chrisalbon">Pinboard</a>]



### Find all the tag pairs with class=logo


```python
soup.find_all(class_='logo')
```




    [<a class="logo" href="http://www.chrisralbon.com/about-chris-albon/"><img alt="Blog Logo" src="/content/images/2014/Feb/chrisalbon_radial-16.png"/></a>]



### Select the string in front of the link nested inside the h2 tag pair


```python
posts = soup.select("h2 > a")
posts[0].string
```




    'Conflict Health Has Shut Down'



### Print the pretty, nested version of the Beautiful Soup object


```python
print(soup.prettify())
```

    <!DOCTYPE html>
    <html>
     <head>
      <meta charset="utf-8" content="text/html" http-equiv="Content-Type"/>
      <meta content="IE=edge,chrome=1" http-equiv="X-UA-Compatible"/>
      <title>
       Chris R. Albon
      </title>
      <meta content="Data for social good." name="description"/>
      <!--[if lt IE 9]>
    			<script type="text/javascript" src="/assets/js/html5shiv.js"></script>
    		<![endif]-->
      <meta content="True" name="HandheldFriendly"/>
      <meta content="320" name="MobileOptimized"/>
      <meta content="width=device-width, initial-scale=1.0" name="viewport"/>
      <link href="http://fonts.googleapis.com/css?family=Lato|Oswald|Open+Sans:300|Merriweather:400,400italic,700,700italic" rel="stylesheet" type="text/css"/>
      <link href="/assets/css/framework.css" rel="stylesheet" type="text/css"/>
      <link href="/assets/css/style.css" rel="stylesheet" type="text/css"/>
      <script type="text/javascript">
       var infinite_conf = {"button_text":"Older posts","no_more_post":"No More Post","enable_infinite":"1"};
      </script>
      <meta content="Ghost 0.4" name="generator"/>
      <link href="/rss/" rel="alternate" title="Chris R. Albon" type="application/rss+xml"/>
      <link href="http://www.chrisralbon.com/" rel="canonical"/>
     </head>
     <body class="home-template">
      <header class="header-section container" style="background-image: url(/content/images/2014/Feb/orange_bg.png)">
       <div class="row">
        <a class="logo" href="http://www.chrisralbon.com/about-chris-albon/">
         <img alt="Blog Logo" src="/content/images/2014/Feb/chrisalbon_radial-16.png"/>
        </a>
        <div class="branding">
         <h1 class="site-title">
          <a href="http://www.chrisralbon.com">
           Chris R. Albon
          </a>
         </h1>
         <p class="site-description">
          Data for social good.
         </p>
        </div>
       </div>
      </header>
      <section class="main-content container">
       <div class="row">
        <div class="post-list">
         <article class="entry-post post">
          <time class="entry-date">
           Feb 16, 2014
          </time>
          <h2 class="entry-title">
           <a href="/conflict-health/">
            Conflict Health Has Shut Down
           </a>
          </h2>
          <p>
           In 2008, I launched the blog Conflict Health to investigate and defend the role of health workers during political violence and armed conflicts. Four years later, I had written almost 500 posts on Conflict Health…
          </p>
         </article>
         <article class="entry-post post">
          <time class="entry-date">
           Feb 14, 2014
          </time>
          <h2 class="entry-title">
           <a href="/about-chris-albon/">
            About Chris Albon
           </a>
          </h2>
          <p>
           Short version: I use data for social good. I also write about it. Longer version: I am the Director of a new crisis data project at Ushahidi, leading our work around the use of data…
          </p>
         </article>
        </div>
        <nav class="pagination clearfix" role="pagination">
         <span class="page-number">
          Page 1 of 1
         </span>
        </nav>
       </div>
      </section>
      <footer class="footer-section container">
       <div class="row">
        <div class="signature">
         <a href="http://www.chrisralbon.com/about-chris-albon/">
          About
         </a>
         |
         <a href="https://twitter.com/chrisalbon">
          Twitter
         </a>
         |
         <a href="https://github.com/chrisalbon">
          GitHub
         </a>
         |
         <a href="https://pinboard.in/u:chrisalbon">
          Pinboard
         </a>
        </div>
       </div>
      </footer>
      <!-- .footer-section -->
      <script src="/public/jquery.js?v=821a9ed878">
      </script>
      <script src="https://google-code-prettify.googlecode.com/svn/loader/run_prettify.js">
      </script>
      <img alt="" hidden="" src="/view.gif?page=/" style="display:none"/>
     </body>
    </html>
