<!--
.. title: first-post
.. slug: first-post
.. date: 2020-07-15 18:10:06 UTC+01:00
.. tags: static site generator, nikola
.. category: nikola
.. link: 
.. description: 
.. type: text
-->

## [Nikola](https://getnikola.com/getting-started.html) A modern static site generator with jupyter notebook help

### Nikol commands used.

```txt 
    1.  > nikola version
    2.  > nikola init --quiet sayyedblogs
    3.  > nikola init --demo sayyedblogs
    4.  > nikola --help
    5.  > nikola build
    6.  > nikola serve  or nikola serve --browser or nikola serve -b or nikola auto
    7.  > nikola new_post
    8.  > nikola new_page
    9.  > nikola new_post -f markdown or -f ipynb
    10. > nikola help new_post
    11. > nikola new_post -F # To list all available format
    12. > nikola new_post -f markdown -t about # new page with about.md created with tile set to about
    13. > nikola theme -l # To get the list of install theme
    14. > nikola theme --list-installed  # to see the list of installed theme
```

### Related Blogs

  + [Nikola-documentation](https://getnikola.com/handbook.html#jupyter-notebook)
  + [By Jiawei Zhaung](https://jiaweizhuang.github.io/blog/nikola-guide/).
  + [Jaako Luttinen](http://www.jaakkoluttinen.fi/blog/how-to-blog-with-jupyter-ipython-notebook-and-nikola/)
  + [by Louistiao](http://louistiao.me/posts/how-i-customized-my-nikola-powered-site/)
  + [ yet to come]()
  + [Bootswatch](https://bootswatch.com/)
  + [Bootswatch](https://bootswatch.com/)
  + [by Mathieu Dugu](https://www.brainsorting.dev/posts/create-a-blog-with-nikola/)
  + [Brian](http://groupbcl.ca/blog/posts/2019/static-site-generator-candidate-software-nikola/)
  + [Randlow](https://randlow.github.io/posts/python/create-nikola-coding-blog/



### How nikola works

- It is a python static site generator that used help from other existing site generators such as hugo and pelican. It has number of small pulgins that do the jobs. [Here](https://plugins.getnikola.com/) is the list of plug in that it uses.
- For example `notebook_shortcode` is a plug in that allows embedding the notebook into the markdown files. But be careful, it may not work and distrub your settings.


### Installing Nikola 

1. Create a Python virtual environment.
2. Either create or choose your working directory, I created `mkdir -p nikola` in my project.
3. Cd into nikola, activate your virtual environment 
4. Install nikola using pip with extras `pip install nikola[extras]`. On windows it takes time.
5. Check the version `nikola version`. I have `v8.1`

### Initialize nikola

1. Run `$ nikola init --quiet sayyedblogs`. This will create a new directoy name `sayyedblogs` and create the following directories and one file. `conf.py  files/  galleries/  images/  listings/  pages/  posts/`.
2. All these directories are empty. The file `conf.py` comes with default installation options available.
3. Get the help run `nikola --help`


```txt
Available commands:
  nikola auto                 builds and serves a site; automatically detects site changes, rebuilds, and optionally refreshes a browser
  nikola build                run tasks
  nikola check                check links and files in the generated site
  nikola clean                clean action / remove targets
  nikola console              start an interactive Python console with access to your site
  nikola default_config       Print the default Nikola configuration.
  nikola deploy               deploy the site
  nikola doit_auto            automatically execute tasks when a dependency changes
  nikola dumpdb               dump dependency DB
  nikola forget               clear successful run status from internal DB
  nikola github_deploy        deploy the site to GitHub Pages
  nikola help                 show help
  nikola ignore               ignore task (skip) on subsequent runs
  nikola import_wordpress     import a WordPress dump
  nikola info                 show info about a task
  nikola init                 create a Nikola site in the specified folder
  nikola list                 list tasks from dodo file
  nikola new_page             create a new page in the site
  nikola new_post             create a new blog post or site page
  nikola orphans              list all orphans
  nikola plugin               manage plugins
  nikola reset-dep            recompute and save the state of file dependencies without executing actions
  nikola rst2html             compile reStructuredText to HTML files
  nikola serve                start the test webserver
  nikola status               display site status
  nikola strace               use strace to list file_deps and targets
  nikola subtheme             given a swatch name from bootswatch.com or hackerthemes.com and a parent theme, creates a custom theme
  nikola tabcompletion        generate script for tab-completion
  nikola theme                manage themes
  nikola version              print the Nikola version number

  nikola help                 show help / reference
  nikola help <command>       show command usage
  nikola help <task-name>     show task usage
```


### Build your site

1. Run `nikola build` since we don't have any contents it will build an empty site.
2. By default `nikola` build a site in `output ` directory. Following files are created

```txt
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/07/2020     01:33                assets
d-----        11/07/2020     01:33                categories
d-----        11/07/2020     01:33                galleries
d-----        11/07/2020     01:33                images
d-----        11/07/2020     01:33                listings
-a----        11/07/2020     01:33           3451 archive.html
-a----        11/07/2020     01:33           3669 index.html
-a----        11/07/2020     01:33             93 robots.txt
-a----        11/07/2020     01:33            736 rss.xml
-a----        11/07/2020     01:33            916 sitemap.xml
-a----        11/07/2020     01:33            745 sitemapindex.xml
```

### Start the server

- Though we have not put any of our contents yet we can start the server `nikola serve --browser`. It starts the browser and serve it on local host port:80000. You can start the server on a different port `nikola server -p 2320`
- When site is built all configuration files are read from `conf.py`, we will refer this file as config file hereafter.
- By default it uses the many options already set to default values.
- Nikola creates a directory named `ouput` where all files and folders are created that is served to the website.
- The landing page is created at the root of the `output` directroy as `index.html`. This page is created automatically.
- It has three sections:
  1. Html `meta-data`
  2. Page `nave-bar` taken from the theme used
  3. Page contents ( not defined yet)
  4. Bottom script.
- Since everything is generated automatically, we are not goingto touch it yet we have to.
- By default Nikola uses `bootblog4` theme, we are going to use a different one.

> Note: Commit time.

```git
sayyed@neuro ~/n/p/n/mysite (dev)> gitcommit -m "@dev:Structure is working."                              (nikola) 
[dev 8c4958e] dev:Structure is working.
 7 files changed, 335 insertions(+), 32 deletions(-)
 create mode 100644 pages/about.rst
 create mode 100644 pages/index.rst
 create mode 100644 posts/001_intro.ipynb
 create mode 100644 posts/002_basics.ipynb
sayyed@neuro ~/n/p/n/mysite (dev)>    
```

