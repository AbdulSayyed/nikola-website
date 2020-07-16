<!--
.. title: ReadMe
.. slug: Read-Me
.. date: 2020-07-10 02:36:27 UTC+01:00
.. tags: markdown, nikola
.. category: markdown
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
  + [Brain Sorting](https://www.brainsorting.dev/posts/create-a-blog-with-nikola/)
  + [Randlow](https://randlow.github.io/posts/python/create-nikola-coding-blog/
  + [By Josh](https://www.joshbialkowski.com/pages/extending.html)



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

### Changing the theme

1. First look at the available theme using ``nikola theme -l`. To see the available commands use `nikola help theme`. Here is the list of installed theme by default. Use ``nikola theme --list-installed` `

```txt
base at /home/sayyed/anaconda3/envs/nikola/lib/python3.8/site-packages/nikola/data/themes/base
base-jinja at /home/sayyed/anaconda3/envs/nikola/lib/python3.8/site-packages/nikola/data/themes/base-jinja
bootblog4 at /home/sayyed/anaconda3/envs/nikola/lib/python3.8/site-packages/nikola/data/themes/bootblog4
bootblog4-jinja at /home/sayyed/anaconda3/envs/nikola/lib/python3.8/site-packages/nikola/data/themes/bootblog4-jinja
bootstrap4 at /home/sayyed/anaconda3/envs/nikola/lib/python3.8/site-packages/nikola/data/themes/bootstrap4
bootstrap4-jinja at /home/sayyed/anaconda3/envs/nikola/lib/python3.8/site-packages/nikola/data/themes/bootstrap4-jinja
```
2. We are going to use `bootsrap4`, take a list what is present there in that directory.

```txt
drwxrwxr-x 4 sayyed sayyed 4096 Jul 10 01:37 ./
drwxrwxr-x 8 sayyed sayyed 4096 Jul 10 01:37 ../
drwxrwxr-x 4 sayyed sayyed 4096 Jul 10 01:37 assets/
-rw-rw-r-- 1 sayyed sayyed  249 Jul 10 01:37 bootstrap4.theme
-rw-rw-r-- 1 sayyed sayyed  492 Jul 10 01:37 bundles
-rw-rw-r-- 1 sayyed sayyed  399 Jul 10 01:37 README.md
drwxrwxr-x 2 sayyed sayyed 4096 Jul 10 01:37 templates/
```
3. The templates directory contains the following.

```txt
drwxrwxr-x 2 sayyed sayyed 4096 Jul 10 01:37 ./
drwxrwxr-x 4 sayyed sayyed 4096 Jul 10 01:37 ../
-rw-rw-r-- 1 sayyed sayyed  655 Jul 10 01:37 authors.tmpl
-rw-rw-r-- 1 sayyed sayyed 6904 Jul 10 01:37 base_helper.tmpl
-rw-rw-r-- 1 sayyed sayyed 3202 Jul 10 01:37 base.tmpl
-rw-rw-r-- 1 sayyed sayyed  440 Jul 10 01:37 index_helper.tmpl
-rw-rw-r-- 1 sayyed sayyed  658 Jul 10 01:37 listing.tmpl
-rw-rw-r-- 1 sayyed sayyed 2318 Jul 10 01:37 pagination_helper.tmpl
-rw-rw-r-- 1 sayyed sayyed 1998 Jul 10 01:37 post.tmpl
-rw-rw-r-- 1 sayyed sayyed 1124 Jul 10 01:37 tags.tmpl
-rw-rw-r-- 1 sayyed sayyed  662 Jul 10 01:37 ui_helper.tmpl
```

4. When nikola uses `nikola new_post` plug in command it uses `post.tmp` defined in `conf.py` file to create the post.

> Note: Before we are going to use this theme, the modern way of using themes is to also customise theme further with `bootswatch` themes as child theme. [Here]() is a list of child themes that we can use with `bootstap4`.

### Subtheming: Using `flatly` bootswatch theme with parent bootstrap4.

- Nikola allows you to use bootstrap watch sub themeing. First you can choose a theme directly of your choice freely from bootswatch.
- Once you have decided the theme, you need to use this command in your root directoy.
- This will crate a folder which would be the name of you custom theme and download the bottswath them. You only need to tell in config file about your custom theme name `theme = 'name of the folder" ` here in this command it is `myflatly`. 
- Run this command from the root directory `nikola subtheme -n myflatly -s flatly -p bootstrap4`

> Note -n indicates the name you decide to give to your custom theme ( it is called a custom theme as you are using a misture of both themes). -s indicates the subthemeing and -p indicats the parent theme.


```txt
sayyed@neuro ~/n/p/n/mysite (dev) [1]> nikola subtheme -n myflatly -s flatly -p bootstrap4                                          (nikola) 
[2020-07-15 16:08:18] INFO: subtheme: Creating 'myflatly' theme from 'flatly' and 'bootstrap4'
[2020-07-15 16:08:18] INFO: subtheme: Downloading: https://bootswatch.com/4/flatly/bootstrap.min.css
[2020-07-15 16:08:18] INFO: subtheme: Downloading: https://bootswatch.com/4/flatly/bootstrap.css
[2020-07-15 16:08:18] INFO: subtheme: Theme created.  Change the THEME setting to "myflatly" to use it.
```

- Nikola creates a new directory `Themes\assests\ css and js files` along with a file called `myflatly.theme`.
- Set the value of `THEME = myflatly` and not to the `bootstrap4`.
- Run the server, if no change is detected. Do the follwoings: make sure in config file no double entires of `THEME = ` are actively present, second rund `nikola clean` and build the site again using either `nikoa auto ` or nikoa server`. If no change is detected, delete the cash files and re run again. If no luck delete the themes directory and re run the subthemeing commands and watch for any error closely.

> Note: Commit our changes.

```txt
[dev 369c59b] dev:New theme is used successfully, bootswatch theme `flatly` installed,it is working.
 5 files changed, 11111 insertions(+), 25 deletions(-)
 create mode 100644 themes/myflatly/assets/css/bootstrap.css
 create mode 100644 themes/myflatly/assets/css/bootstrap.min.css
 create mode 100644 themes/myflatly/myflatly.theme
 ```

### Adding submenue in Kikola

- Sub menus are added in nested tuple. So if I need to have a menu with sub menu. First thing to note that I would need the third tuple where the entries will go. Say I have a menue with title `My Blog` and uder this menu, I have two entries say `ABC` and `DEF`. Then

```txt
(
  (( ("/blog/","ABC"),("/pages/about/","DEF") ), "My Blogs"),
)
```

- The last entry in a tuple `MY Blogs` is the main menu title, while the other two entries `ABC` and `DEF` are the submenu's title. When these submenues are pressed they take to the files they are pointing to.
- Similarly if I want more menus I have to add them accordingly. 

### Creating navigation links in menu bar

- The menu bar does not have any links that we want. I have the following menus to my page. Add the follwoing the to the config file.Comment the old values.

```txt
NAVIGATION_LINKS = {
    DEFAULT_LANG: (
        (
            (   
               ("/categories/python/", "Python"),
               ("/categories/neuroscience/", "Neuroscience"),
               ("/categories/nipype/", "Neuroimaging in Python"),
            ),
            "My Blogs"
        ),
        (
            (
                ("/about/", "About"),
                ("/pages/publication/", "Publications"),

            ),
            "About"
        ),
        
        ("/archive/", "Archives"),
        ("/rss.xml", "RSS feed"),
        ("/categories/index.html", "Tags"),
    ),
}
```
- The setting is such that I have three different types of posts, with different category. Nikola can have only one category at one time.
- I have set `python,neuroscience, and nipype` to start with. And I would want my files to be arranged according to thier categores. Thus I have set three different paths. These paths tell nikola that when I press the submenu name `Neuroimaging in Python` of the main menu name `My Blogs` the file that well be srved comes from `/catagories/cat_nipype/` folder.


### Arragning default psts

- Since I werite two kinds of files one uses markdown and the other uses notebooks and I would lke to keep the `notebooks` seprate. I have amended the follwoing section of config file according to my needs.

```txt
# type,source,template
POSTS = (
    ("notebooks/*.ipynb", "notebooks", "post.tmpl"), # This line is added by me
    ("posts/*.rst","psots","post.tmp"), # It is necessary for short codes.
    ("posts/*.md", "posts", "post.tmpl"),
    ("posts/*.txt", "posts", "post.tmpl"),
    ("posts/*.html", "posts", "post.tmpl"),
)
PAGES = (
    ("pages/*.rst", "pages", "page.tmpl"), # Do not delete it.
    ("pages/*.md", "pages", "page.tmpl"),
    ("pages/*.txt", "pages", "page.tmpl"),
    ("pages/*.html", "", "page.tmpl"), # It is omitted so that landing html does not end up in pages floder.
    #("notebooks/*.ipynb", "", "page.tmpl") # This line is added by me
)

```

- The very first line in posts `("notebook/*.ipnb","notebooks","post.tmpl")` says that when a new notebook is cerated it is created in the root floder called `notbook` that we will create in next steps, the seconed entry tells that when website is served the notebooks post will be served from `nootbooks` directroy and the template used is `post.tmpl`.

- Once the above settings are done, creating a simple notebook in a right folder is done using `nikola new_post -f ipynb -t 003_basics`. The new notebook will be created in the `notebook` folder and will be seved from `output/notebook/` folder.

- Nikola automatically adds in necessary meta data that is needed for jupyter notebook to be published as a post, the following sectin is added in notebook file.

```txt
"nikola": {
      "category": "nipype",
      "date": "2020-07-10 15:43:54 UTC+01:00",
      "description": "",
      "link": "",
      "slug": "001_intro",
      "tags": "python, jupyter, nipype",
      "title": "001_intro",
      "type": "text"
    }
```

- The vale of category is left empty that is needed to be filled. This file can be opened in any json editor and ameneded.
- No authoer field is added it can be done by adding the fololowing code in the config file.

```txt
ADDITIONAL_METADATA = {
    'author': 'Abdul Sayyed',
    'summary': ''
}

```
- Once this is added in config file, a new created post will have the additional entreis as shown below

```txt
"nikola": {
   "author": "Abdul Sayyed",
   "category": "",
   "date": "2020-07-15 19:24:30 UTC+01:00",
   "description": "",
   "link": "",
   "slug": "test2",
   "summary": "",
   "tags": "",
   "title": "test2",
   "type": "text"
  }
```

### Catageories in Nikola

- 





 ### Nikola **landing page**

 - When nikola starts it reads `conf.py`, one of the values set there is of `INDEX_PATH = ""`. By default it is set to have no value, then when server starts it serve the site from the root directory of the websit that is `output/`. This page is generated automatically depending upon the configuration set in config files.
 - Run nikola in auto mode which is to to livereload method, and change the value of this variable to post `INDEX_PATH = post` and watch the landing page is changed accrodingly.

 1. Create a page using `nikola new_page -f html -f index`