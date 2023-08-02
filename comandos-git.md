# Git Notes

***

## Notes

<br>

***HEAD***: present state of the code

***working tree***: where the files are being stored and edited

***index***: where the commits are being stored, in between the working tree and the Git repository

***.gitignore file***: file with a list of the names of files which shall not be tracked. Must be added to the project.

***commit***: saving state of the tracked files.

> It is interesting to only commit when the piece of work done is well functioning in the code

***push***: uploading commits to the project on a branch.

***branches***: separated working lines where the commits are sent ("pushed") to be stored. They don't speak to one another if not explicitly commanded so. The *main* branch, which used to be called *master*, is usually where the whole official project is stored.


<br>

## Git commands

***

> All expressions in between <> ought to be replaced with expressions following as suggested inside it.

Initialize Git repository in a folder:

    git init

> To initialize a Git repository as a changes only storing repository, use git init --bare

Change user's name locally/globally:

    git config --local user.name "<user-name>""

    git config --global user.name "<user-name>"

Change user's email locally/globally:

    git config --local user.email <user-email>

    git config --global user.email <user-email>

Check on changes (on files) which are or aren't ready to be commited, and untracked files:

    git status

Add file to be commited:

    git add <file-name>

Add ALL tracked files to be commited:

    git add .

Commit:

    git commit

Commit with message:

    git commit -m "<message>"

Check on committing history:

    git log

Check on resumed committing history:

    git log --oneline

Check on extended committing history:

    git log -p

Check on committing history as a graph:

    git log --graph

> Other commands to personalize history view on terminal can be seen in [git log cheatsheet](https://devhints.io/git-log)

Check on remote repositories linked to the local repo:

    git remote

Check on the path of remote repositories linked to the local repo:

    git remote -v

Link local repo to an existing remote repository:

    git remote add <remote-repository-name> <path-to-the-remote-repository>

> The path to the remote repository can be either a local path, or a server URL, an internet URL or an intranet link/path.

> The remote repository on GitHub (or any other online repository) is mostly called origin.

Change name of a remote repository:

    git remote rename <old-remote-repository-name> <new-remote-repository-name>

Clone a remote Git repository to an existing folder:

    git clone <path-to-the-remote-repository>

Clone a remote Git repository to a new folder:

    git clone <path-to-the-remote-repository> <folder-name>

Update local repository referring to a specific branch from the remote repository:

    git pull <remote-repository-name> <branch-name>

> If both the local and remote repository have been altered independently, so as to the local repo has changes which the remote repo don't *and* vice versa, then execute git pull --rebase < remote-repository-name > < branch-name >

Push all commits to the remote repository on a specific branch:

    git push <remote-repository-name> <branch-name>

> On both git pull and git push, the remote repository name can be replaced by the path to the remote repository as listed in previous quote.

Establish specific remote repository as to where all pushes are sent when on specific branch:

    git push -u <remote-repository-name> <branch-name>

> After this command, push command can be executed as simply *git push*, when on the specified branch, to push to the specified remote repository.
