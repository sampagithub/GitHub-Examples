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

> You'll need to generate a Personal Access Token (PAT)
https://github.com/settings/token

You will use the PAt as your password when you login

- Give it access to Contents for Commits

### SSH

```sh
git clone git@github.com:Sampayob/GitHub-Examples.git
cd GitHub-Examples
ssh-keygen -t rsa
```

Name the ssh key with the full path: /home/user/.ssh/new_ssh_key and inspect the key to copy it to Settings->SSH and GPGkeys: 

```sh
cat /home/user/.ssh/new_ssh_key.pub
```

To check connectivity:

```sh
ssh -T git@github.com
```

If it dont works, try:

```sh
eval `ssh-agent`
ssh-add /home/andrew/.ssh/alt-github_id_rsa
```

### GitHub CLI

Install the CLI

eg. Linux (Ubuntu)

```sh
(type -p wget >/dev/null || (sudo apt update && sudo apt-get install wget -y)) \
	&& sudo mkdir -p -m 755 /etc/apt/keyrings \
	&& wget -qO- https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
	&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
	&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
	&& sudo apt update \
	&& sudo apt install gh -y
```

Generate SSH key

```sh
ssh-keygen -t rsa 
# key name with full path: /home/user/.ssh/new_ssh_key.pub
```

Login into GitHub

```sh
gh auth login
gh repo clone Sampayob/GitHub-Examples
```

## Commits


Set the global editor
```sh
git config --global core.editor emacs
```

Make a commit and commit message without opening an editor
```sh
git commit -m "add another change"
```


## Branches

List of branches

```sh
git branch
```

Create a new branch

```sh
git branch branch-name
```

Checkout the branch

```sh
git checkout branch-name
```

Push new branch to remote

```sh
git push -u origin branch-name
```

## Remotes

We can add remotes but often you will just add remote via upstream when adding a branch

```sh
git remote add
git branch -u origin new-branch
```
git branch -u origin new-

## Stashing

```sh
git stash list
git stash
git stash save my-name
git stash apply
git stash pop
```

## Merging

```sh
git checkout branch-name
git merge desired-branch
```

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