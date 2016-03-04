Title: Convert All Jupyter Notebooks In A Folder To Basic HTML Using Bash
Date: 2016-12-01 12:00
Category: Command Line
Tags:
Slug: covert_all_ipynb_to_html
Authors: Chris Albon
Summary: Convert All Jupyter Notebooks In A Folder To Basic HTML Using Bash

```python
%%bash
# #!/bin/bash

# activates a python 3.x environment called py3k
source activate py3k

# sets the working directory to the current directory
cd "$(dirname "$0")"

# converts all iPython Notebook files to basic html
for f in *.ipynb; do jupyter nbconvert --to html --template basic $f; done
```

    discarding /Users/chrisralbon/anaconda/envs/py3k/bin from PATH
    prepending /Users/chrisralbon/anaconda/envs/py3k/bin to PATH
    [NbConvertApp] Using existing profile dir: '/Users/chrisralbon/.ipython/profile_default'
    [NbConvertApp] Converting notebook covert_all_ipynb_to_html.ipynb to html
    [NbConvertApp] Support files will be in covert_all_ipynb_to_html_files/
    [NbConvertApp] Loaded template basic.tpl
    [NbConvertApp] Writing 2959 bytes to covert_all_ipynb_to_html.html
    [NbConvertApp] Using existing profile dir: '/Users/chrisralbon/.ipython/profile_default'
    [NbConvertApp] Converting notebook list_all_files_and_folders_in_a_directory.ipynb to html
    [NbConvertApp] Support files will be in list_all_files_and_folders_in_a_directory_files/
    [NbConvertApp] Loaded template basic.tpl
    [NbConvertApp] Writing 2123 bytes to list_all_files_and_folders_in_a_directory.html
