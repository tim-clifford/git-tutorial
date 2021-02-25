# Git Tutorial
Just the basic stuff you need to know for simple git usage.

## Installation and launching

**Linux**

If you're using linux you probably know what you're doing. If not, just... use
your package manager...?

**Windows**

The simplest solution is to use Git Bash, which you can get from [the official
download page](https://git-scm.com/download). The default options are fine.

A more extensible solution is to install Windows Subsystem for Linux (WSL),
which is a full Linux installation in a virtual machine. (If you think this is
too much, just use Git Bash)

You may also be interested in downloading the _Windows Terminal_ from the
Microsoft Store.

**MacOS**

The must-have package manager on MacOS is [Homebrew](https://brew.sh), which
you can install by

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Then you can install packages through

```sh
brew install <package>  # suggestions: git (of course), python, wget...
```

> If you encounter a permission error, be cautious when you copy and paste
> solutions from StackOverflow. Ask @WeixuanZ to make sure you don't mistakenly
> give root privileges to all files in `/usr/local/`.


## What to do if you get stuck
As the old adage goes... RTFM. `man git` should be your best friend. Run it on
any terminal where you use git. It's much better than any online tutorial you
will ever find. there are also manpages for each of the git commands, try `man
git-add`, `man git-commit`, and so on.

The manpages should come first, but do ask someone knowledgeable if you still
can't figure it out (or if they're nice and willing to help).

## How to exit vim!
Occasionally git commands will open vim. My advice is to learn vim, you'll
thank me later. If you really want to just exit, the following will work every
time. (there are simpler ways when you know what you're doing).

Type \<ESC\>:qa!\<Enter\>, where \<ESC\> and \<Enter\> are the escape and enter
keys respectively.

## The very basics
**To make a new repository**
```sh
git init
```

**To add a file (make git aware of it)**
```sh
git add file
```

**To add all files in the current directory**
```sh
git add .
```

**To commit (make your changes final)**
```sh
git commit -m "Commit message"
```

**To push (upload your changes)**

For the first time
```sh
git push --set-upstream origin master
```

Then after that
```sh
git push
```

**To clone a repository (get it from a remote e.g. github)**

This will make a new directory `project` with the latest code
```sh
git clone https://github.com/username/project
```

**To pull (update your code to the latest from the remote)**
```sh
git pull ## from within the project directory
```

## Basic usage of branches
**To create a new branch based on the current branch**
```sh
git checkout -b branch-name
```
**To switch branches**

Try to keep the working tree clean when doing this or it will get complicated.
```sh
git switch branch-name
```
**To push a branch**
```sh
git push origin branch-name
```
**To open a pull request (basically "please add this code to the master branch")**

The easiest way is to go to github.com, navigate to the page for your
repository, open the branch you want to merge, and click the icon to open a
pull request.

## Basic usage of submodules
To fetch submodules (after cloning the repo)
```
git submodule update --init
```
To add a submodule
```
git submodule add https://github.com/IDP-L211/repo-name
```
To update all submodules to the latest commit
```
git submodule update --remote
```
To completely remove a submodule (yes it is this annoying)
```
git submodule deinit repo-name
# now delete the relevant lines in .gitmodules
rm -rf .git/modules/repo-name
```

## Instructions for basic terminal usage
**BEWARE: files deleted on a terminal will not go to the recycle bin**

N.B. Launching Git Bash from Windows puts you in "C:\\Users\\username" (written
as `~`) when you start it. Launching a linux or MacOS terminal usually puts you
in "/home/username" (also written as `~`).

**To go to a directory**
```sh
cd directory
```
You can use either a full path e.g. `/home/user/directory` or
`/c/Users/user/directory` or a relative path

**To make a directory**
```sh
mkdir directory
```
where again directory can be a full path or relative path

**To delete a file**
```sh
rm file
```

**To delete a folder**
```sh
rm -r folder
```
