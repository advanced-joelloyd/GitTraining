GETTING STARTED
===============

Installing Git
--------------
[https://git-scm.com/downloads](https://git-scm.com/downloads)


Windows Tools for Git
---------------------

###Cmder
[http://gooseberrycreative.com/cmder](http://gooseberrycreative.com/cmder/)

###Git Bash
Installed by default with Git for Windows

###GUIs
[https://git-scm.com/downloads/guis](https://git-scm.com/downloads/guis)


git config
----------

Set your name and email for all the repositories on your computer with:

`git config --global user.name "Firstname Lastname"`

`git config --global user.email "youremail@whatever.com"`

Now any commits you make will show up with your name attached.


WORKING LOCALLY
===============

git init
--------

git status
----------

git add
-------

git commit
----------

git log
-------

git show
--------

git diff
--------

git stash
---------

git reset
---------

git revert
----------

git rm
------

gitignore
---------


WORKING WITH YOUR OWN REMOTE
============================

SSH on Windows
--------------
[https://help.github.com/articles/generating-ssh-keys](https://help.github.com/articles/generating-ssh-keys/)

Your SSH keys will be stored in `C:\Users\YourAccountName\.ssh\`.  If the `.ssh\` folder doesn't exist, don't worry.

`ssh-keygen -t rsa -b 4096 -C "youremail@whatever.com"`

Press `Enter` to save your key in the default folder.

Enter a passphrase for your key.

Open the folder `C:\Users\YourAccountName\.ssh\` and copy the contents of the new `.pub` file.

This is the SSH key you will need to add to your remote repository, e.g. GitHub, so it can authenticate your access.

git remote
----------

git push
--------


WORKING WITH OTHERS
===================

git clone
---------

git pull
--------

git mergetool
-------------


GLOSSARY
========

###Commit

###HEAD

###Repository, Repo

###Remote


FURTHER READING
===============

GitHub Git Cheat Sheet
----------------------
[https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf](https://training.github.com/kit/downloads/github-git-cheat-sheet.pdf)

Try Git
-------
[https://try.github.io](https://try.github.io/)

Video Learning
--------------
[http://www.pluralsight.com/courses/git-fundamentals](http://www.pluralsight.com/courses/git-fundamentals)