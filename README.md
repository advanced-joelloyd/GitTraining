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


WORKING LOCALLY
===============


Create a new repo
-----------------
`git init`

This creates a new Git repository in your current working folder.

A hidden `.git/` folder will appear at the top level.  All Git data is contained in this top-level folder.

The repository is self-contained, and can be moved and copied anywhere and remain intact.


See your repo's current state
-----------------------------
`git status`

This shows you all uncommitted changes, including:

* Staged changes - changes that will be included in your next commit
* Unstaged changes - changes to files in your repo that you have not staged
* Untracked files - files that don't exist in your repo


Stage your changes to be committed
-----------------------------
`git add`

Use `git add` to track files and stage changes.  You must specify what changes you want to stage, e.g.

* `git add myfile.txt` stages any changes to the file `myfile.txt`
* `git add *.txt` stages any changes to files with the extension `.txt`
* `git add src/` stages any changes to files in the folder `src/`

You can also stage all changes and new files by using:

* `git add --all`

Use `git status` to see which files you've staged.  

Staged files will be in green.  

Untracked files and unstaged changes will be in red.


Commit your changes
-------------------
`git commit`

Use `git commit -m "A commit message"` to save all staged changes to your local repository as a single changeset with an attached message.

If you don't supply the `-m` switch, Git will prompt you for a commit message by thrusting you into the Vim text editor.

Don't panic!

If you know how to use Vim, great!

If not, carefully type `:q!` to exit Vim and try again.  

Now you can correctly enter `git commit -m "A commit message"` and your changes will be saved.

###Shortcuts!

You can stage all unstaged changes and commit them in one command with:

`git commit -a -m "A commit message"`

This can be shortened again to:

`git commit -am "A commit message"`

Note: this will not affect untracked files.  You will need to `git add` any untracked files to include them in your commit.


See commit history
-----------------------
`git log`

This shows you a list of all the commits on your current branch.

Each commit has its own unique commit ID.

You can scroll up and down the history using `Page Up` and `Page Down`.

Press `Q` to exit the history and go back to the command line.

You can see just a range of history, e.g.

* `git log -n 5` shows the five most recent commits
* `git log --since="45 minutes ago"` shows commits going back forty-five minutes
* `git log --since="2 months 3 weeks 1 day 2 hours 30 minutes 59 seconds ago"` shows commits going back nearly three months
* `git log --after="2015-01-07"` shows commits after the 7th July 2015
* `git log --before="2015-01-07"` shows commits before the 7th July 2015

`git log` has a lot more switches for more specific searches.

You can see the full range at [https://git-scm.com/docs/git-log](https://git-scm.com/docs/git-log).


See details for a commit
------------------------
`git show`

Use `git show <commitid>` to see the changes in a single commit.  

Replace `<commitid>` with a commit ID, which you can see from `git log`.


See your uncommitted changes
-------------------------------
`git diff`

This shows you the uncommitted changes in your working directory.

* `git diff` shows changes not yet staged
* `git diff --cached` shows what will be committed if you commit now without staging anything else, i.e. `git commit -m`
* `git diff HEAD` shows what will be committed if you staged everything, i.e. `git commit -am`

It can also be used to see differences between commits and branches.  See the full documentation at [https://git-scm.com/docs/git-diff](https://git-scm.com/docs/git-diff.)

Shelve your uncommitted changes
-------------------------------
`git stash`

This stores the current changes in your repo, then undoes the changes so your working directory is unchanged.

You can then recover the stashed changes at a later point.

* `git stash list` shows you all of your stashed changesets
* `git stash pop` applies the changes from the most recent stash back to your working directory, and removes that stash, aka 'unstash'
* `git stash drop` deletes the most recent stashed changeset
* `git stash clear` deletes all of your stashed changesets


Create a new branch in your repo
--------------------------------
`git branch`

Use `git branch <branchname>` to create a new branch in your local repository.

The new branch will be based on the branch you were in when you branched.  `master` is the default branch that all repos have.

The new branch will have all of the commits from up to the point where you branched.

You can delete a local branch with `git branch -d <branchname>`.


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