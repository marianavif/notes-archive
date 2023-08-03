# Git Notes

***

## Notes

<br>

***HEAD***: current state of the code

***working tree***: where the files are being stored and edited

***index***: where the commits are being stored, in between the working tree and the Git repository

***.gitignore file***: file with a list of the names of files which shall not be tracked. Must be added to the project.

***commit***: saving state of the tracked files. Also referred to as "state".

> It is interesting to only commit when the piece of work done is well functioning in the code

***commit hash***: alphanumeric code to which corresponds a single commit. Can be checked on *git log*.

***push***: uploading commits to the project on a branch.

***branches***: separated working lines where the commits are sent ("pushed") to be stored. They don't speak to one another if not explicitly commanded so. The *main* branch, which used to be called *master*, is usually where the whole official project is stored.

***merge***: creating a commit which contains all the work from the current branch updated with the work from a specific branch. Only the current branch is altered, while the other branch's history remains intact.

***rebase***: updating the current branch with the work from a specific branch *without creating a commit out of it*. The two branches turn into one, with the other branch being erased during the process. The other branch's commits history is not preserved.

***stash***: saving changes for later, without committing.

***tag****: checkpoint which results in a *version* of the project, changes made after that will be included on later versions.

***release***: launched version of the project which can be cloned or downloaded by anyone with the link to it. Can be done only manually, via GitHub website.

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

Add file to be commited (staging):

    git add <file-name>

Add ALL tracked files to be commited:

    git add .

Remove changes on tracked files which weren't added to be commited:

    git restore <file-name>

Remove changes on tracked files which were added to be commited (unstaging):

    git restore --staged <file-name>

Commit:

    git commit

Commit with message:

    git commit -m "<message>"

Check on committing history:

    git log

> Type *q* on command line to exit.

Check on resumed committing history:

    git log --oneline

Check on extended committing history:

    git log -p

Check on committing history as a graph:

    git log --graph

> Other commands to personalize history view on terminal can be seen in [git log cheatsheet](https://devhints.io/git-log)

Undo commits:

    git revert <commit-hash>

> Edit the reverting message, type *:x* and press enter to exit.

Check on the difference between current file and the last commited version of the file (before adding it to commit):

    git diff

Check on the difference between two commits:

    git diff <oldest-commit-hash> <most-recent-commit-hash>


Check on remote repositories linked to the local repo:

    git remote

Check on the path of remote repositories linked to the local repo:

    git remote -v

Link local repo to an existing remote repository:

    git remote add <remote-repository-name> <path-to-the-remote-repository>

> The path to the remote repository can be either a local path, or a server URL, an internet URL or an intranet link/path.

> The remote repository on GitHub (or any other online repository) is mostly called origin.

Change name of a remote repository:

    git remote rename <current-remote-repository-name> <new-remote-repository-name>

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

Create a new branch:

    git branch <new-branch-name>

Work on an other branch:

    git checkout <other-branch-name>

Create a new branch and work on it:

    git checkout -b <new-branch-name>

Merging a specific branch to the current branch:

    git merge <specific-branch-name>

> Edit the merging message, type *:x* and press enter to exit

Rebasing a specific branch to the current branch:

    git rebase <specific-branch-name>

Saving changes for later, without committing (stash):

    git stash

Checking on list of stashes:

    git stash list

Applying changes saved on stash:

    git stash apply 0

Removing the stash from the top of the list (stash{0}):

    git stash drop

> Although it seems plausible applying not necessarily the first stash of the list {0}, it did not work trying to apply them out of order. Apply the top one, drop it and the second of the list will become the first and so on.

Apply changes saved on stash and remove it from the list of stashes:

    git stash pop

Move through states of the project:

    git checkout <commit-hash>

> Remember to create a new branch if it proves necessary to make changes in the project from a previous state.

Tag the project:

    git tag -a <tag-name> -m "<message>"

> Usually, the tag name is the number of the version.

Check on the list of tags:

    git tag

Send a tag to the remote repository:

    git push <remote-repository-name> <tag-name>
