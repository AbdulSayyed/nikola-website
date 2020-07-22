<!--
.. title: nipype-workflow
.. slug: nipype-workflow
.. date: 2020-07-21 18:24:13 UTC+01:00
.. tags: 
.. category: nipype
.. link: 
.. description: 
.. type: text
.. author: Abdul Sayyed
.. summary: 
-->

## My setup of nipype

- I have successfully created a conda environment for `nipype`. it is located here ().
- The directory I have chosen to work is `/nikol/` the listing is given as below.

```py
⋊> ~/n/p/nikola ll                                                                                                         (base) 17:32:36
total 52K
drwxrwxr-x 12 sayyed sayyed 4.0K Jul 10 21:35 demosite/
drwxrwxr-x  6 sayyed sayyed 4.0K Jul 18 00:27 Ex_01/
-rw-rw-r--  1 sayyed sayyed  28K Jul 16 18:15 installed-moudle.txt
drwxrwxr-x 13 sayyed sayyed 4.0K Jul 21 18:23 mysite/
lrwxrwxrwx  1 sayyed sayyed   31 Jul 21 16:11 nik-nip-vscode -> ./.vscode/Nikola.code-workspace
-rw-rw-r--  1 sayyed sayyed 8.1K Jul 16 18:13 requirement.txt
⋊> ~/n/p/nikola    
```

- The `demosite` I do not need and it will be deleted.
- Mysite directory is the main directory of nikola blog.
- The `vsocde workspace` is saved in `.vscode` folder and pointed by `nik-nip-vscode` link ( it is uselss at this moment)

### How `notebook` differs when created in `nikola` or in `jupyterlab`?

1. Notebook can be created in many ways. But when nikola does its scanning it throws an error if it does not find the meta data it requires for a notebook  to be a part of the nikola.
2. It does not matter where it can be created from, the meta data can be easily added. Inorder for nikola to open and work with notebook, it has to have some meta data inside it. It is not a rocket science as I had gread difficulty dealing with notebook when trying to open them with pelican or embed them in markdown file. Though I have not been successful to embed notebooks in markdown files using short code as described by nikola docuemtation.
3. Follwing is a meta data entries when the file is created by jupter lab selecting particular ipython kernel. Ipython kernil is just a python interpreter name that you have created in your conda or pip environment and given it a uniqure name. For exampe when I created `nipype` environment I installed different version of differnt software that can work together. This version is knows as your particular python kernel or interpreter.

```py
"metadata": {
  "kernelspec": {
   "display_name": "Python (nipype)", # This is added when you choose you particular python kernel
   "language": "python",
   "name": "nipype"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.8.2"
  }
```

4. The above detail is enough for jupyter to open the file but not for nikola needs to know more to deal with correct theme and template to open notebook data. Follwing information is needed and can simply be added into the above meta data.

```py
"nikola": {
   "author": "Abdul Sayyed",
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
### How to create a notebook with vscode.

1. Using command pattlet we can use `> create notebook` command. There are other worth exploring as of importing as well.
2. Running notebook in vscode and setting it properly can be handy. The scroll bar shows, wchic environmen is selected. If the wrong one is selected, by clicking on the status bar on the infromation it will open different environment where the right one can be opened. Once the right one is opened. The notebook already have installed module such as `numpy, matplot or nipype` exposed api avilable to use.
3. On the right hand top corner, vscode also shows the local server and the right kernel selected.
4. It is very handy that in my one `notebook` folder created in `nikola` top level directories, I can have different notebooks set and ready to be used with different environments.
5. They can all be opened from one place and knows which environment they are to be used as in their meta contents this information is saved.
6. If not the right kernel can be opened from the right corner.

### How this repo is committed

1. Since I am using nikola, whatever I do I keep the work under `mysite` folder so that it is also published as well.
2. I always work in dev branch. To publish my site , I switched to `src` by using `git checkout src` from here I use `nikola github_deploy`. This takes care of eveything and only deploy the output folder and whatever is necessary to produce a websit.
3. I also wanted to be able to use my repo with windows so I cloned it to my windwos environment but realised that it does not have any contents, it is only a publish html file repo. No markdown contents.
4. To resolve this issue I had to create a new repo which I named `https://github.com/AbdulSayyed/nikola-website` and added a remote in my local `dev` branch where I usually work from.
5. To add a new remote to a same repo I used this command `git remote add niksrc https://github.com/AbdulSayyed/nikola-website.git` as shown below. Now I have my dev branch set to a remote repo name `nikola-website.git`. This branch is added or referenced in my config file as `niksrc`. To pus or pull I would use `git push niksrc dev` or `git pull niksrc dev`

```git
 ~/n/p/n/mysite on dev  git remote add niksrc https://github.com/AbdulSayyed/nikola-website.git                      (nikola) 12:59:21
⋊> ~/n/p/n/mysite on dev  git remote -v                                                                                (nikola) 12:59:43
niksrc	https://github.com/AbdulSayyed/nikola-website.git (fetch)
niksrc	https://github.com/AbdulSayyed/nikola-website.git (push)
origin	https://github.com/AbdulSayyed/AbdulSayyed.github.io.git (fetch)
origin	https://github.com/AbdulSayyed/AbdulSayyed.github.io.git (push)
⋊> ~/n/p/n/mysite on dev  git status                                                                                   (nikola) 12:59:49
On branch dev
nothing to commit, working tree clean
⋊> ~/n/p/n/mysite on dev  git push -u niksrc dev                                                                       (nikola) 13:00:10
Username for 'https://github.com': Abdulsayyed
Password for 'https://Abdulsayyed@github.com': 
Enumerating objects: 111, done.
Counting objects: 100% (111/111), done.
Delta compression using up to 8 threads
Compressing objects: 100% (97/97), done.
Writing objects: 100% (111/111), 259.39 KiB | 7.63 MiB/s, done.
Total 111 (delta 41), reused 6 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (41/41), done.
To https://github.com/AbdulSayyed/nikola-website.git
 * [new branch]      dev -> dev
Branch 'dev' set up to track remote branch 'dev' from 'niksrc'.
⋊> ~/n/p/n/mysite on dev ◦ git remote -v                                                                               (nikola) 13:01:08
niksrc	https://github.com/AbdulSayyed/nikola-website.git (fetch)
niksrc	https://github.com/AbdulSayyed/nikola-website.git (push)
origin	https://github.com/AbdulSayyed/AbdulSayyed.github.io.git (fetch)
origin	https://github.com/AbdulSayyed/AbdulSayyed.github.io.git (push)
⋊> ~/n/p/n/mysite on dev ◦    
```

> The reason it was done because I was having difficulty with shared folder with VBox and Ubuntu 20.04. As there are some material, especially some images that I wanted to use with nikola site.

- Though I have started working from both machine, I need to understand that I can only work or update the contents from one machine, push it to the remote. And then when starting to work again in another machine I need to pull a repo and started woking with it. I can not start to wrok in both machine with the same repo as it would created confilicts and I will loose my work.

