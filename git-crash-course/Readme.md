## GitHub Hidden Folder
There is a hidden folder `.git` which tells you that our project is a git repo.

If we want to create a git repo in a new project we will create the folder and then initialize that repo using `git init`
```sh
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
code Readme.md 
# code Readme.md to open it
git status
# git status to see what files are tracked or untracked
git add .
git status
# make changes to Readme.md
git commit -m "add Readme file"
```
## Cloning
>We can clone in three ways : 
> 1. HTTPS
> 2. SSH
> 3. Github CLI

Since we are using Github Codespaces we'll create a temporary directory(tmp) in our workspace

```sh
mkdir /workspace/tmp
cd /workspace/tmp
```

1. ### HTTPS
```sh
git clone https://github.com/Avi6201123/GitHub-Foundation.git
cd OST-demo
```
> You will need to generate a Personal Access Token(PAT)
Security --> Developer's Setting --> Personal Access Token --> Fine-grained PAT  
https://github.com/settings/tokens

You will use the PAT as your password when you login and username same as Github username.
- For permission : Give it access to Contents for Commits

2. ### SSH
```sh
git clone git@github.com:Avi6201123/GitHub-Foundation.git
cd OST-demo
```
In local machine you will need to create our own SSH rsa key pair.
```sh
ssh-keygen -t rsa
```
We can test our connection here : 
```
ssh -T git@github.com
```
For WSL users if you create a non default key you might need to add it.
```sh
eval `ssh-agent`
ssh-add /home/avan/.ssh/alt-github_id_rsa
# In my case, ssh-add /home/pixel/Sites/github-alt_id_rsa
```

3. ### Github CLI
Install the CLI,
eg. Linux(Ubuntu)
```sh
sudo apt update
sudo apt install gh
```
If its unable to locate the package, use this
```sh
(type -p wget >/dev/null || (sudo apt update && sudo apt-get install wget -y)) \
&& sudo mkdir -p -m 755 /etc/apt/keyrings \
&& wget -qO- https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y
```

```
gh auth login
gh repo clone Avi6201123/GitHub-Foundation
```

## Commits
When we want to commit code we can write git commit which will open up the commit edit message in the editor of choice. This is already configured to run in VS code. If you run in local machine it will complain to set a default editor.
```sh
git commit
```

Set the global editor

```
git config --global core.editor emacs
```

Make a commit and commit message without opening an editor
```
git commit -m "Add another exclamation mark"
```
## Branches
1. List of branches
```sh
git branch
```
2. Create a new branch
```sh
git branch <branch-name>
```
3. Checkout a branch 
```sh
git checkout <branch-name>
```
```sh
git push -u origin <branch-name>
# -u --> --set-upstream 
```
## Remotes

## Stashing

## Merging

## Add
When we want to stage changes that will be included in the commit
We can use the . to add all possible files.
```sh
git add Readme.md
git add .
```
## 

## Reset 
Reset allows you to move staged changes to be unstaged. 
This is useful when you want to revert all files not to be committed.

```sh
git add .
git reset
```
> git reset will revert a git add.

## Status

Git status shows you what files will or will not be committed.
```
git status
```
## Log
git log will show recent git commits to the git tree.
```
git log
```

## Gitconfig
The gitconfig file is what stores your global configuration for git such email, name and more
Showing the contents of our .gitconfig file.
```
git config --list 
```
OR
```
git config --list --show-origin
```
When you first install Git on a machine you are suppose to set up your name and email
```sh
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

## Push 
when we want to push a repo to our remote origin
```
git push
```