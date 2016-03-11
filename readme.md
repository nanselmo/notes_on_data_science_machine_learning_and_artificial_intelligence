# Data Science Peripheral Brain

## What is a peripheral brain?

In medical education, a "peripheral brain" is respoitory for all the informaton young doctors must know, but is too much to keep in their heads. I am a data scientist and political scientist, and this repository is my peripheral brain.

## How can I use it?

More specifically, this repo is a Pelican site for my personal homepage, [ChrisAlbon.com](http://chrisalbon.com). You can use it by going there or (if you are so inclined) forking this repo.

## What template do you use?

It is a custom Pelican bootstrap template I made specifically for ChrisAlbon.com. You can [view the repo here](https://github.com/chrisalbon/simple_library).

## Open Issues
- Fix Jupyter Notebooks Naming
- Fix Command Line Notebook Naming
- Add Bug Reporting Via Github
- Add Search

# Deployment Procedure

$ pelican content -o output -s pelicanconf.py
$ ghp-import output
$ git push origin gh-pages
