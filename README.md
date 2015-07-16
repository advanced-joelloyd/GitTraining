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

####Shortcuts!

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

You can see a list of your local branches with `git branch`.

Use `git branch <branchname>` to create a new branch in your local repository.

The new branch will be based on the branch you were working in when you branched.  `master` is the default branch that all repos have.

The new branch will have all of the commits from up to the point where you branched.

You can delete a local branch with `git branch -d <branchname>`.


Change your current working branch
----------------------------------
`git checkout`

Use `git checkout <branchname>` to change your working branch to `<branchname>`.

Any uncommitted changes will be not be changed.

####Shortcut!

You can create a new branch and switch to it immediately using `git checkout -b <branchname>`.


Set your repo to a point in its history
---------------------------------------
`git checkout`

As well as switching branches, you can use `git checkout` to move to a particular point in your commit history.

* `git checkout <commitid>` changes all the files in your local repo to match everything as it existed at the time of the given `<commitid>`

You can return to normal with `git checkout <branchname>`.


Merge changes from one branch into another
------------------------------------------
`git merge`

Use `git merge <branchname>` to merge changes from the branch `<branchname>` into the branch you are currently working in.

If there are no merge conflicts, the changes from `<branchname>` will be copied to your working branch.

You can see the new commits using `git log`.

If there are merge conflicts, you will need to resolve the conflicts, and then either:

* `git merge --abort` to undo any merged changes and go back to before you merged
* `git commit -m "A commit message"` to commit the conflict changes and complete the merge.


Use a 3rd party tool to resolve merge conflicts
-----------------------------------------------
`git mergetool`

Git does not have a build-in tool for resolving merge conflicts.

You can plug in your favourite and the `git mergetool` command will drive it to display any outstanding merge conflicts.

You can plug in your preferred mergetool by opening the file `C:\Users\YourUsername\.gitconfig` and adding the following section:

	[merge]
	    tool = kdiff3
	[mergetool "kdiff3"]
    	cmd = \"C:\\\\Program Files (x86)\\\\KDiff3\\\\kdiff3\" $BASE $LOCAL $REMOTE -o $MERGED


WORKING WITH REMOTE REPOSITORIES
================================

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

This allows you to manage links with other repositories - usually a mirror that one or more people are synchronising their changes through, e.g. GitHub.

* `git remote -v` shows you a list of remote links with an alias (usually `origin`)
* `git remote add <alias> <url>` adds a link to the url with the given alias, e.g. `git remote add origin https://github.com/advanced-joelloyd/GitTraining.git`
* `git remote remove <alias>` removes the link called `<alias>`, e.g. `git remote remove origin`

There is a convention to call your repo's default remote mirror `origin`, and you will see this in most examples.  

It is only a convention.  If you want to call your remote `pineapple` you can do so and it will be local to you.


Send your changes to a remote repo
----------------------------------------
`git push`

This allows you to send your local commits to a remote repository.

If you have created a new repo or branch locally, use `git push -u <alias> <branchname>` to push it to the remote repo for the first time.  `-u` will link your local branch with the remote and make synchronising changes easier.

For any other use, `git push <alias> <branchname>` will send your changes to the remote.

If there are commits on the remote that you do not have in your local repo, your `push` will be cancelled and you will need to `pull` the changes.


Get and merge changes from a remote repo to your local repo
-----------------------------------------------------------
`git pull`

Use `git pull <alias> <branchname>` to retrieve commits on the remote repo that you don't have locally.

It will fetch the changes and automatically `git merge` them into your local repo.

If there are any merge conflicts, you will need to deal with them as per `git merge` above.


Get a local copy of a remote repo
---------------------------------
`git clone`

Use `git clone <url>` to get a fresh local copy of a remote repository.

It will automatically create a local repo, get the latest changes and set the remote links for you.


FIXING MISTAKES
===============

Discard your local changes
--------------------------
`git checkout`

Use `git checkout .` to discard all of your uncommitted changes.

It will not delete untracked files.


Deleting untracked files
------------------------
`git clean`

This allows you to delete untracked files from your local repository, e.g., left-over merge files, build artifacts, log files.

* `git clean -f` removes every untracked file
* `git clean -fd` removes every untracked file and folder


Undo your staging
--------------------------------
`git reset`

Use `git reset` on its own to undo any staging you have done.

This essentially reverses the `git add` command.

It does not affect any of your uncommitted changes.


Undo committed changes
----------------------
`git revert`

This allows you to reverse the changes in existing commits with a new commit.

* `git revert HEAD~1` creates a new commit that reverses the changes in your last commit
* `git revert HEAD~3` creates a new commit that reverses the changes in your third-last commit
* `git revert HEAD~3..HEAD~1` creates a new commit that reverses the changes from your last to third-last commit

You will then be able to view the undo commits in your history with `git log`.

This is a safe way of undoing committed changes if they have already been pushed to a remote repo.


Deleting commit changes
-----------------------
`git reset`

As well as unstaging changes, `git reset --hard` can be used to completed delete commits from your local repo.

* `git reset --hard HEAD~1` deletes the most recent commit
* `git reset --hard HEAD~3` deletes the last three commits

BEWARE: the deleted commits disappear, so you are rewriting history.  This command is best used only on local commits.


Remove files from your repository
----------------------------
`git rm`


Stop Git from tracking files and folders
---------
`.gitignore`


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
