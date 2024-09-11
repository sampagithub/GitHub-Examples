## Git Hidden Folder

There is a hidden folder called `.git`which tells you that our project is a git repo.

If we wanted to create a git repo in a new project, create the project folder and initialize that repo using `git init`.

```sh
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
code Readme.md
# git status
# git add .
git commit -a -m "add readme file"
# git reset

```

## Cloning

We can clone three ways: HTTPS, SSH, GitHub CLI

Since we are using GitHub Codespaces, we'll create a temporary directory in our workspace

```sh
mkdir /workspace/tmp
cd /workspace/tmp
```

### HTTPS

```sh
git clone https://github.com/Sampayob/GitHub-Examples.git
```

## Commits

## Branches

## Remotes

## Stashing

## Merging

## Add

When we want to stage changes that will be included in the commit. We can use the `.` to add all possible fiels

```
git add Readme.md
git add .
```

## Reset

Reset allows you to move Staged changes to be unstaged. This is useful when you want to revert all files not to be not commited.

```
git add .
git reset
```
> git reset will revert a gid add.

## Status

`git status` shows you what files will or will not be commited.

```
git status
```