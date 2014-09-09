learning-git
============
How do you create a new project/repository?
A git repository is simply a directory containing a special .git directory.

This is different from "centralised" version-control systems (like subversion), where a "repository" is hosted on a remote server, which you checkout into a "working copy" directory. With git, your working copy is the repository.

Simply run git init in the directory which contains the files you wish to track.

For example,

cd ~/code/project001/
git init
This creates a .git (hidden) folder in the current directory.

To make a new project, run git init with an additional argument (the name of the directory to be created):

git init project002

(This is equivalent to: mkdir project002 && cd project002 && git init)
To check if the current current path is within a git repository, simply run git status - if it's not a repository, it will report "fatal: Not a git repository"

You could also list the .git directory, and check it contains files/directories similar to the following:

$ ls .git
HEAD         config       hooks/       objects/
branches/    description  info/        refs/
If for whatever reason you wish to "de-git" a repository (you wish to stop using git to track that project). Simply remove the .git directory at the base level of the repository.

cd ~/code/project001/
rm -rf .git/
Caution: This will destroy all revision history, all your tags, everything git has done. It will not touch the "current" files (the files you can currently see), but previous changes, deleted files and so on will be unrecoverable!
