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

```git config --global user.name "Firstname Lastname"```

```git config --global user.email "youremail@whatever.com"```

Now any commits you make will show up with your name attached.


GLOSSARY
========

###Commit

###Repository, Repo

###Remote


WORKING LOCALLY
===============


Create a new repo
-----------------
`git init`


See your repo's current state
-----------------------------
`git status`


Stage your changes to be committed
-----------------------------
`git add`


Commit your changes
-------------------
`git commit`


See commit history
-----------------------
`git log`


See details for a commit
------------------------
`git show`


See your uncommitted changes
-------------------------------
`git diff`


Shelve your uncommitted changes
-------------------------------
`git stash`


Set your repo to a point in its history
---------------------------------------
`git checkout`


Undo your uncommitted changes and staging
--------------------------------
`git reset`


Undo committed changes
----------------------
`git revert`


Remove files from your repository
----------------------------
`git rm`


Stop Git from tracking files and folders
---------
`gitignore`


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


Manage links with remote repos
-------------------------------------
`git remote`


Send your changes to a remote repo
----------------------------------------
`git push`


WORKING WITH OTHERS
===================

Get a local copy of a remote repo
---------------------------------
`git clone`


Get and merge changes from a remote repo to your local repo
-----------------------------------------------------------
`git pull`


Use a 3rd party tool to resolve merge conflicts
-----------------------------------------------
`git mergetool`


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