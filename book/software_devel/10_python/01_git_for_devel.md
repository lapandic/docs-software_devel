# Git for development {#git status=draft}

## Background reading

- [Git handbook](https://guides.github.com/introduction/git-handbook/)
- [GitHub bootcamp](https://help.github.com/categories/bootcamp/)
- [Git branching](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
- [Git cheatsheet](https://services.github.com/on-demand/downloads/github-git-cheat-sheet/)


## GitHub repository

A repository, or Git project, encompasses the entire collection of files and folders associated with a project, along with each file’s revision history.[^f1]

The main Duckietown repository is https://github.com/duckietown/Software/

## Fork a repository

In order to make changes in the repository you need to fork it. Open the previous link and in the upper right corner click fork.

## Clone a repository

Now you should have a forked copy of the repository on your own account. To clone it on your computer open the terminal and execute:

    $ git clone git@github.com:USERNAME/REPOSITORY.git duckietown

This will clone your forked repository named `REPOSITORY` to a local folder named `duckietown`.

## Create a new branch

We want to avoid making and committing changes directly on the master branch, to prevent overriding someone else's work. That is why we create new branches. Note that the master branch in Software repository is protected and you will not be able to push your changes directly to it.
To create a new branch and switch to it execute:

    $ git checkout -b ![branch-name]

The new branch is created on top of the master branch. You can check on which branch are you by executing:

    $ git status

or

    $ git branch

To switch to another existing branch execute:

    $ git checkout ![branch-name]

## Commit and push changes

After you are done with your work you want to commit and push those changes. You can check the status and see that there can be some files waiting to be added (untracked files) or those files that were there are modified and waiting to be committed. In order to add the files:

    $ git add ![file-path]

or

    $ git add -A

to add all new untracked files.

Now to stage and commit the changes run:

    $ git commit -a -m "![commit-message]"

If you check the status now, you will see that your branch is ahead of remote branch for one commit. To push that commit execute:

    $ git push origin ![branch-name]

## Create a pull request

In order to merge your changes in the main repository, navigate in the browser to your forked repository and the branch where you pushed your changes.
Click on a button `New pull request` and make sure that the base fork is `duckietown/*` and head fork is your repository, then click `Create pull request`. Please make sure that you comment your changes as they need to be reviewed and approved by Duckietown moderators.

## References

[^f1]: See [Git handbook](https://guides.github.com/introduction/git-handbook/) (accessed 15.10.2018)
