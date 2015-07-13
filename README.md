GETTING STARTED WITH GIT
========================

Installing Git
--------------
[https://git-scm.com/downloads](https://git-scm.com/downloads)


Windows Tools for Git
---------------------

###Cmder
[http://gooseberrycreative.com/cmder](http://gooseberrycreative.com/cmder/)

A good all-purpose command line tool for Windows.  Personal favourite as a Git client on Windows as it bridges the gap between Windows and Linux command line tools.

###Git Bash
Installed by default with Git for Windows.  Provides a bash terminal with syntax highlighting.

###cmd.exe
You can use a standard Windows command prompt if you prefer.  References to Git will need to be in your %PATH% variable, which the Git installer can do for you.

###GUIs
[https://git-scm.com/downloads/guis](https://git-scm.com/downloads/guis)
A range of Git GUI clients for all OSes.


git config
----------

Set your name and email for all the repositories on your computer with:

`git config --global user.name "Firstname Lastname"`

`git config --global user.email "youremail@whatever.com"`

Now any commits you make will show up with your name attached.


GLOSSARY
========

###Commit

###Repository, Repo

###Remote


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

Authentication
--------------

Most hosted remote repositories, e.g. GitHub, will offer at least HTTPS and SSH as ways of authenticating when you are pushing and pulling changes

###HTTPS
Authenticating to remote repositories with HTTPS is simple - you authenticate with a username and password.  Some Git GUI clients will remember your username and password for you.

HTTPS is a bit simpler to get started with on Windows.

###SSH on Windows
[https://help.github.com/articles/generating-ssh-keys](https://help.github.com/articles/generating-ssh-keys/)

SSH is a little more work to set up on Windows, but offers a similar experience to HTTPS

[https://help.github.com/articles/which-remote-url-should-i-use](https://help.github.com/articles/which-remote-url-should-i-use/)


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