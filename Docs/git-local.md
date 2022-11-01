## Introducing Git

To understand git workflow Log into github account from terminal

```bash
git config --global user.name "Your Name"
git config --global user.email "
```

Check the configuration

```bash
git config --list
```
check git version

```bash
git --version
```

Check current logged in user

```bash
git config user.name
```
To display git help use:

```bash
git help
```
### Managing Application Source Code with Git
>Git version control features a branching model to track code changes. A branch is a named reference to a particular sequence of commits

>All Git repositories have a base branch named master. By default, when you create a commit in your repository, the master branch is updated with the new commit

cd to the directory where you want to create a new repository and initialize it with git

```bash
git init
```
when changes are made to the files in the repository, you can see the changes by using the git status command

```bash
git status
```
To add changes to the staging area, use the git add command

```bash
git add .
```
To commit changes to the repository, use the git commit command

```bash
git commit -m "commit message"
```
To view the commit history, use the git log command

```bash
git log
```
>By convention, the master branch in a Git repository contains the latest, stable version of the application
source code. To implement a new feature or functionality, create a new branch from the master branch. This
new branch, called a feature branch, contains commits corresponding to code changes for the new feature.
The master branch is not affected by commits to the feature branch.

To create a new branch, use the git branch command

```bash
git branch feature1
```
To switch to the new branch, use the git checkout command

```bash
git checkout feature1
```
To create a new branch and switch to it, use the git checkout -b command

```bash
git checkout -b feature1
```
To merge the feature branch into the master branch, use the git merge command

```bash
git merge feature1
```
To delete a branch, use the git branch -d command

```bash
git branch -d feature1
```
To push changes to the remote repository, use the git push command

```bash
git push
```
To pull changes from the remote repository, use the git pull command

```bash
git pull
```

