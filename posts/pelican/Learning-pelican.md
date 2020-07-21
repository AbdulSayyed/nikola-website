Title: Learning-pelican
Date: 2020-07-05 12:40
Status: published
Category: python
Tags: python, blogging, pelican
Slug: Fourth-Post
Authors: Abdul Sayyed
Summary: Learning pelican static site generator


## What are we using to build a site.

1. [Pelican](https://blog.getpelican.com/) library installed with 
2. Markdown parsing library
3. Jinja2, a template engine
4. pip or conda virtual environment that a user create where the above are installed and kept serprately.
5. Other buildig tools
    1. [Flask tutorial](https://blog.miguelgrinberg.com/). A web framework.
    2. [Green unicorn or gunicorn](https://www.fullstackpython.com/green-unicorn-gunicorn.html) is web server Gateway implementation (WSGI) tha tis used to run Python web aaplication.
    3. [Jinja2](https://www.fullstackpython.com/jinja2.html). An implementation of a template engine.This link contains many useful sites.


## What guides are available to use.

1. [Full Stack Python](https://www.fullstackpython.com/blog/python-3-flask-green-unicorn-ubuntu-1604-xenial-xerus.html)
2. 





### Building a Basic site.

1. Select your working director, or cd into it.
2. Create a virtual env, if not created. Activate your environment
3. First `conda install pip`. It will install the following

```txt
he following NEW packages will be INSTALLED:

  _libgcc_mutex      conda-forge/linux-64::_libgcc_mutex-0.1-conda_forge
  _openmp_mutex      conda-forge/linux-64::_openmp_mutex-4.5-0_gnu
  ca-certificates    conda-forge/linux-64::ca-certificates-2020.6.20-hecda079_0
  certifi            conda-forge/linux-64::certifi-2020.6.20-py38h32f6830_0
  ld_impl_linux-64   conda-forge/linux-64::ld_impl_linux-64-2.34-h53a641e_5
  libffi             conda-forge/linux-64::libffi-3.2.1-he1b5a44_1007
  libgcc-ng          conda-forge/linux-64::libgcc-ng-9.2.0-h24d8f2e_2
  libgomp            conda-forge/linux-64::libgomp-9.2.0-h24d8f2e_2
  libstdcxx-ng       conda-forge/linux-64::libstdcxx-ng-9.2.0-hdf63c60_2
  ncurses            conda-forge/linux-64::ncurses-6.1-hf484d3e_1002
  openssl            conda-forge/linux-64::openssl-1.1.1g-h516909a_0
  pip                conda-forge/noarch::pip-20.1.1-py_1
  python             conda-forge/linux-64::python-3.8.3-cpython_he5300dc_0
  python_abi         conda-forge/linux-64::python_abi-3.8-1_cp38
  readline           conda-forge/linux-64::readline-8.0-hf8c457e_0
  setuptools         conda-forge/linux-64::setuptools-49.1.0-py38h32f6830_0
  sqlite             conda-forge/linux-64::sqlite-3.32.3-hcee41ef_0
  tk                 conda-forge/linux-64::tk-8.6.10-hed695b0_0
  wheel              conda-forge/noarch::wheel-0.34.2-py_1
  xz                 conda-forge/linux-64::xz-5.2.5-h516909a_0
  zlib               conda-forge/linux-64::zlib-1.2.11-h516909a_1006


```
> Note : pip and python both are installed. keep a record of `pip -V` and `python --version`

3. Install pelican, the latest guide is [here](https://docs.getpelican.com/en/stable/install.html). It uses this command `pip install pelican[Markdown] `. Though it gives this error

```
ERROR: nbconvert 5.6.1 requires entrypoints>=0.2.2, which is not installed.
ERROR: bleach 3.1.5 requires packaging, which is not installed.

```


4. It can be installed seprataley.  Install pelican and markdown parsing  libraries with pip ,e.g., `pip install pelican==3.7.1 markdown==2.6.8`
    - Installing pelican would install `feedgenerator, jinja2, pygments, docutils, pytx, blinker and unidecode`
    - Optionally you can install using pip other librarirs lke `piloow, beautifulsoup4, cssmin, cssprefixer, cssutil, pretty, six, smartypans and typogrify webassets`

> Time to time it can be upgraded `pip install --upgrade pelican`


    
4. Start pellican `pelican-quickstart`

```txt
   Where do you want to create your new web site? [.] 
> What will be the title of this web site? nipype
> Who will be the author of this web site? Abdul Sayyed
> What will be the default language of this web site? [en] 
> Do you want to specify a URL prefix? e.g., https://example.com   (Y/n) Y
> What is your URL prefix? (see above example; no trailing slash) http://AbdulSayyed.github.io/jupyter-pelican
> Do you want to enable article pagination? (Y/n) y
> How many articles per page do you want? [10] 5
> What is your time zone? [Europe/Paris] Europe/London
> Do you want to generate a tasks.py/Makefile to automate generation and publishing? (Y/n) y
> Do you want to upload your website using FTP? (y/N) n
> Do you want to upload your website using SSH? (y/N) n
> Do you want to upload your website using Dropbox? (y/N) n
> Do you want to upload your website using S3? (y/N) n
> Do you want to upload your website using Rackspace Cloud Files? (y/N) n
> Do you want to upload your website using GitHub Pages? (y/N) y
> Is this your personal page (username.github.io)? (y/N) y
Done. Your new project is available at /home/sayyed/neuro-science/projects/nipype
```


5. Following files are created.
    
```py
Makefile          pelicanconf.py
content/           publishconf.py output/
``` 

- make command is used to genereat/start many task such as , making html, cleaning, regenerating serving etc. It is generated according to the input which we have used while creating a basic infrasturcture.
  - content/ directory is used to write markdown contents wile other two files are for configuation.

6. Run `make html` and the contents of our markdown file will be converted into html in a newly created directory called `output`. You can also run `pelican content` to generate HTML.
7. Run `make serve` and server will start on a local host post on port 8000. You can cd into output directory and run `python -m pelican.server`
8. You can also use `pelican -s pelicanconf.py -o output content` to make html instead of make html
9. You can cd to ouput then use `python -m http.server`
10. Write your post in **content/** directory using post or blog or any other directory like **code/** etc and keep your post or articles seprate.
11. If using sublime use this [package] `https://packagecontrol.io/packages/Pelican`. Once installed use `Ctr+shift+p` and write `pelican` help wil come. You can cofigure the metadata.

### The contents of pelican conf file

```txt
#!/usr/bin/env python
# -*- coding: utf-8 -*- #
from __future__ import unicode_literals

AUTHOR = 'Abdul Sayyed'
SITENAME = 'Neuroimaging in Python'
SITEURL = ''

PATH = 'content'

TIMEZONE = 'Europe/London'

DEFAULT_LANG = 'en'

# Feed generation is usually not desired when developing
FEED_ALL_ATOM = None
CATEGORY_FEED_ATOM = None
TRANSLATION_FEED_ATOM = None
AUTHOR_FEED_ATOM = None
AUTHOR_FEED_RSS = None

# Blogroll
LINKS = (('Pelican', 'http://getpelican.com/'),
         ('Python.org', 'http://python.org/'),
         ('Jinja2', 'http://jinja.pocoo.org/'),
         ('You can modify those links in your config file', '#'),)

# Social widget
SOCIAL = (('You can add links in your config file', '#'),
          ('Another social link', '#'),)

DEFAULT_PAGINATION = 5

# Uncomment following line if you want document-relative URLs when developing
#RELATIVE_URLS = True


```

### Running your site

- `make html` and `make serve` are two main commands.
- First time is run the out put is below

[//]:#(![image](pleican-server-01))


### Adding first post 

1. Created `first.md` in content folder `echo "# First markdown post" >>./content/first.md`
2. Add follwoing meta dat at the top.

```txt
Title: My First Post
Date: 2020-07-05 12:40
Status: published
Category: nipype
Tags: python, neuroscience
Slug: First-Post
Authors: Abdul Sayyed
Summary: Alcohol apophenia nodal point dead plastic long-chain hydrocarbons lights neon. Dome sub-orbital DIY render-farm youtube systema katana tiger-team shrine tank-traps paranoid pre--ware soul-delay boy voodoo god gang. Beef noodles market papier-mache faded skyscraper-ware numinous disposable sub-orbital sunglasses Kowloon math. Render-farm dome digital media tube girl DIY drugs 3D-printed network refrigerator wristwatch construct papier-mache sign.

```

- The output is bleow.

[//]:#(![image](pleican-server-02))


2. Added and committed then push to remote.

### Adding functionality for `jupyter notebook`

- First create a repo and committ then start working with dev branch

```
git init .
git add --all
git commit -m "@master: initial commit"
git checkout -b dev

```
- Install a plug in from [danielfrg/pelican-jupyter](https://github.com/danielfrg/pelican-jupyter)
- First create a plug in folder `mkdir -p plugins` 
- Down load or clone somewhere temporarily and only copy `pelican_jupyter` folder into your plugin folder.


### Inform your config file about the plugins

- open `pelicanconf.py` and add the following after the last line.

```
MARKUP = ("md", "ipynb")

from pelican_jupyter import markup as nb_markup
PLUGINS = [nb_markup]
IPYNB_MARKUP_USE_FIRST_CELL = True

IGNORE_FILES = [".ipynb_checkpoints"]


```
- Now the structure is ready to pubish a notbook.
- Install `jupyter lab`
- `conda install jupyterlab`, it wil install all other requirement for the job.
- Start `jupyter lab`
- Write your first notebook with an extension of `.ipynb`, in order for this book to be published directly it has to have markdown in first cell. Add the follwoing in first cell and in other cell carry on doing some pyton work.

```
- title: My notebook
- author: John Doe
- date: 2018-05-11
- category: pyhton
- tags: pip


```
- Save and close the juptyer lab 
- Run `make html` and you will get some kind of error.

```
CRITICAL: ModuleNotFoundError: No module named 'pelican_jupyter'

```
- Since our plugins is a part of this module that we did not install as it is in developing stages.
- Now install `pip install pelican_jupyter`
- Run and start the server
- You should see your `.ipynb` running directly as a blog post.
- The output is as follows


[//]:#(![image](pleican-server-02))

- In order to get live reload install `invoke` using `pip install invoke` along with `livereload`
- Then start your server with `invoke livereload`.
-


### Adding [themes](https://github.com/getpelican/pelican-themes)

1. Using [pelican-bootstrap3](https://github.com/getpelican/pelican-themes/tree/master/pelican-bootstrap3). Clone it in main directory 
2. Add the following in your `pelicanconf.py`.

```txt

THEME = 'pelican-themes/pelican-bootstrap3'
JINJA_ENVIRONMENT = {'extensions': ['jinja2.ext.i18n']}

```
### Adding new plugins  to the pelicanconf.py

3. To implement i18n, you need to include the plugins. The best choice is [i18n_subsites](https://github.com/getpelican/pelican-plugins/tree/master/i18n_subsites) plugin.

4. Since we already have the directory `plugins` where our plugins are kept. We do not need to have all the plugins which are present. But to first get them locally. You need to add the whole repo locallely

5. clone it recusively `git clone --recursive https://github.com/getpelican/pelican-plugins`
6. Add follwoing line to your `pelicanconf.py` file

```txt
# plugins
PLUGIN_PATHS = ['./plugins']
PLUGINS = ['i18n_subsites']

```
7. Copy paste `i18n_subsites` folder into you `plugins/` folder. Once done rebuilt the site and run the server.

8. Notice the change, now new theme is working.

![](/pelican-server-04)

---

### Customising the views

- New custom `.css` and `.js` files are added in a new folder under `content\extra`.
- We need to tell `pelicanconf.py` where are they stroed.
- Add the following contents in the config file

```py
pelicanconf.py

CUSTOM_CSS = 'static/css/custom.css'
CUSTOM_JS = 'static/js/custom.js'

STATIC_PATHS = [ 'extra' ]

EXTRA_PATH_METADATA = {
    'extra/custom.css': {'path': 'static/css/custom.css'},
    'extra/custom.js': {'path': 'static/js/custom.js'}
}


```

### Adding pages to the site 

- Pages are not post but about you or the sites.
- Create a new folder under `content/pages` and add a new file called `about.md`.
- Tell config file about the pages, add the following to your config file

```
# Paths
PATH = 'content'
PAGE_PATHS = ['pages']
ARTICLE_PATHS = ['posts']

# Top menus
DISPLAY_CATEGORIES_ON_MENU = False
DISPLAY_PAGES_ON_MENU = True

```

> if every thing is working then use this below.

### Creating a sample notebook

1. Start jupyter notebook or jupyter lab from nipype env, but it will give error a they are not installed in this envioronment.

> Note: To avoid this problem, you need to install ipykernel i your environment `pip insall --user ipykernel`

