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

