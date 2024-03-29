---
title: Git it right
author: simon
date: 2023-02-21 21:00:00 +0100
categories: [Computer Science]
tags: [Git, Github, Version Control, Terminal]
math: true
mermaid: true
image:
  path: /images/2023-02-18-gititright/colston.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: 2020, June, 7th, Bristol, UK. The outrage from people sparked by George Floyd's death in the US has spread to the UK. A statue of Edward Colston, the former master of Society of Merchant Venturers, a slave trader, is pulled down by protesters from city centre and dragged through the streets before being thrown into the harbour. Three days later, The statue is pulled up and kept at M shed. Same year, Github announced that they would rename its master branch to main.
---

Git was developed by Linus Torvalds during the [**fathering of Linux in 2005**](https://en.wikipedia.org/wiki/Git#History). It is a distributed version control system, meaning you can tracked the changes of your files and folders in a project and easily switch between different versions. it is now a standard tool for industrial project development. Collaborators can work on the same project at the same time with different versions. As a product from the biggest advocate of the [**Open-source-software movement**](https://thenewstack.io/linus-torvalds-on-why-open-source-solves-the-biggest-problems/), Git is made all free and open source. It 
is a great tool to track personal projects and tidy up the drive(no more "final_version", "final_version2", "final_final_version"...). <br/>
Github/Gitlab are the most popular platforms for storing Git repositories. Technically git can track any type of files, small block of codes/texts to large images or videos. As long as there is change in the file directory, git can track it. However, it is not recommended to track large files with git, since all historical changes are stored in the .git folder, even if an images is deleted after commits, the git storage size will still be the same, which is not ideal to upload to Github/Gitlab or other cloud hosting services. <br/>
In this post, I will introduce the basic usage of git and how to communicate with cloud hosting services like Github/Gitlab. This post can also be used as look up table or cookbook for future use. <br/>

> "Git" in Turkish language means "go; move"
{: .prompt-info }

To-do in this post:
- [x] Git installation
- [x] Git commands
- [x] Git configurations
- [x] Git with Github/Gitlab
- [ ] Git with VScode
- [ ] Git illustration diagram

## Git installation

Windows:
: 
Install Git <a href="https://git-scm.com/download/win" target="_top">here</a>, just follow the default installation settings. <br/> 

Linux:
: 
It only makes sense that git is already installed in Linux. If not, <br/>
```bash
sudo apt install git-all
```

Once installed, you can check the version of git by typing in the terminal:
```bash
git --version
```

## Track the changes
Go to a directory you want to track, either empty or with files/folders in it.<br/>
**Initialize a git repository:**
```bash
git init
```

Once you have done some changes in the directory, any untracked changes will appear in <span style="color:red">red</span>. <br/>
**Check any changes in the directory:**
```bash
git status
```

The changes can be added to the staging area, which is a temporary area where you can review the changes before committing. It's like a shopping cart, you can add/remove items before you check out. <br/>
**Add the changes to the staging area:**
```bash 
git add <file_name> # add a specific file
git add . # add all files, or git add -A/-all
git add -u # update the changes to in the files that are already tracked
```

If you changed your mind and don't want to track the changes. <br/>
**Remove the file stage status from the staging area:**
```bash
git restore --staged <file_name> # remove a specific file stage status
git rm --cached <file_name> # remove a specific file stage status, most cases the same as above
git rm --cached -r . # remove all files stage status
```

If you changed your mind about the modifications to some files <br/>
**Remove the file changes:**
```bash
git restore <file_name> # remove the file changes
```

**Remove files:**
```bash
rm <file_name> # remove the file it is not yet tracked
git rm <file_name> # remove the file and add to staging area
```

Once you are happy with the changes, the changes will appear in <span style="color:green">green</span> in the staging area. You can commit the changes to the local repository. e.g. Checkout at the cashier with the items in the shopping cart<br/>
**Commit the changes to the local repository:**
```bash
git commit -m "commit message" # commit the changes with a message
git commit -am "commit message" # add and commit the changes with a message
```

**Check all the commit history:**
```bash
git log # check the commit history
git log --oneline # check the commit history in one line
git log --stat -m # check the commit history with pathes.
```
press ```q``` on keyboard to exit the log.

If you regret the commit, and want to undo the commit. You have to specify which commit you want reset back to, the current commit is named ```HEAD```, its previous commit is ```HEAD^``` or ```HEAD~1```, the second previous commit is ```HEAD~2``` and etc. Another way to specify commit is to use ```<commit id>```, you can check the commit id by using ```git log``` and the id is in <span style="color:orange">orange</span>. You can copy any number of digits you want to call a commit id, but it has to be at least 4 digits.<br/>
**Undo commit:**
```bash
git update-ref -d HEAD # Delete the initial commit after the first commit
git reset --soft HEAD~1 # Undo the last commit keep the changes in staging area
git reset --hard HEAD~1 # Undo the last commit and discard the changes
git revert <commit id> # Create a new commit explicitly to undo that commit
git commit --amend # Modify the last commit message
```

**Compare file or commit changes**
```bash
git diff # compare the files changes before staging
git diff --staged # compare the files changes after staging before commit, equivalent to --cached
git diff <commit id> <commit id> # compare the changes between two commits
```

There are also ways to temporarily save the changes without committing, which is called ```stash```. <br/>
**Stash the changes:**
```bash 
git stash # stash the changes
git stash save "stash message" # stash the changes with a message
git stash list # check the stash list
git stash apply # apply the last stash
git stash drop # remove the last stash from the stash list
git stash pop # apply the last stash and remove it from the stash list
git stash clear # remove all the stashes from the stash list
git stash show # show the last stash changes
```

For some large files, you might want to ignore the changes to the file. It may cause unreasonably large git storage size. <br/>
**Ignore files are not preferred to be saved:**
```bash
touch .gitignore # create a .gitignore file
echo "file_name" >> .gitignore # add the file name to the .gitignore file
echo "*.log" >> .gitignore # ignore all the files with .log extension
```

## Branching
Branching is one of the most useful features of git. It allows you to create a new branch based on the current working state of the repository. And you can make changes to the new branch without affecting the current branch. Once you are happy with the changes, you can choose to merge the new branch to the current branch, or graft features in different commits. <br/>
![Desktop View](/images/2023-02-18-gititright/timestone.gif){: width="500" height="281"}
_My favorite way to think about what does branching do_
**Create a branch**
```bash
git branch <branch_name> # create a new branch
git checkout <branch_name> # switch to the new branch
git checkout -b <branch_name> # create a new branch and switch to it
git branch -d <branch_name> # delete the branch
git branch # check the branch list
```

There is also a way to create a snapshot of current working state. It is sort of like a branch, but more often it is used for a milestone checkout. It's called ```tag```. ```tag``` branch will not be affected by any commits unless forced being renamed. <br/>
**Create a tag**
```bash
git tag <tag_name> # create a new tag
git tag -a <tag_name> -m "tag message" # create a new tag with a message
git tag -d <tag_name> # delete the tag
git tag -a -f <tag_name> <commit id> # force rename the tag to a specific commit
git checkout <tag_name> # switch to the tag
git tag # check the tag list
```

When you want to combine two branches together, you can use ```merge```. Commits from second branch will join merging branch if there is no conflict. Bear in mind, when anything that is not added to staging area and committed, it is in the ```head``` state. Anything in the ```head``` state will be not be merged to the current branch and stay in the staging area.<br/>
**Merge the branches**
```bash
git merge <branch_name> # merge the branch to the current branch
git merge --no-ff <branch_name> # merge the branch to the current branch as a new commit
git merge --squash <branch_name> # merge the branch to the current branch as a new commit with all the changes in one commit, note the changes will be in the staging area
```

Another way to combine the branches is to use ```rebase```. Rebasing allows a linear log history. It is useful when you want to keep the log history clean and easy to read.<br/>
**Rebase the branches**
```bash
git rebase <branch_name> # rebase the current branch to the branch
git rebase -i <branch_name> # rebase the current branch to the branch with interactive mode
```

## Configurations
We don't need to configure anything to use git, but it is recommended to do so if you are collaborating with others visa online hosting services like github. <br/>
**Configure the user name and email**
```bash
git config --global user.name "user name" # configure the user name
git config --global user.email "user email@domain.com" # configure the user email
git config --global color.ui auto # configure the coloring in command line
git config --global --list # check the global configurations
```

Another thing we can do is to set aliases for the commands in git, just to make our life easier. <br/>
**Set aliases for the commands**
```bash
git config --global alias.<alias_name> <command> # set alias for the command
#common aliases
git config --global alias.st status # set alias for status
git config --global alias.ci commit # set alias for commit
git config --global alias.br branch # set alias for branch
git config --global alias.co checkout # set alias for checkout
git config --global alias.unstage 'reset HEAD --' # set alias for unstage
git config --global alias.lg "log --oneline --decorate --all --graph" # set alias for log
```

## Remote Repository
Remote repository is a repository that is hosted online used for saving local repos or collaboration with other users. A remote repository should first be created online first. For example in github, you can go to your main page and click the ```+``` button on the top right corner and select ```New repository```. Then you can follow the instructions to create a new repository. Or you can create a online repo by forking an existing repo, which will make a copy of the existing repo to your account. <br/>
With an repo in your hosting service, you can then clone the repo to your local machine by HTTPS or SSH. Different hosting services may have different way to config HTTPS authentication, in github, HTTPS connections does not support using account and password in terminal anymore from August 2021, you will have to setup a [**Personal Access Token**](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) (PAT) to authenticate. Following will show a more secure protocol by using SSH. <br/>
**Generate SSH key**
```bash
ssh-keygen -t ed25519 -C user.email@domain.com # generate a new ssh key
```
Note that ```-t ed25519``` is the encryption algorithm, Some people also use older algorithms such as ```rsa```. ```-C``` is the comment for the email address you used in github. <br/>
```bash
$ Generating public/private ed25519 key pair.
$ Enter file in which to save the key (C:\Users\simon/.ssh/id_ed25519): 
```
You can press enter to use the default location.<br/>
```bash
$ Created directory 'C:\\Users\\xxx/.ssh'.
$ Enter passphrase (empty for no passphrase):
```
You can also optionally set a passphrase for the key if you are extremely cautious, otherwise press enter. <br/>
**Add the public key on Github**
Once generated, the terminal should tell you where the key is saved, usually it is in ```~/.ssh```. In ```~/.ssh``` folder, you should see two files, ```id_ed25519``` and ```id_ed25519.pub```. The first one is the private key, and the second one is the public key. You should never share your private key. And you can upload the public key to ```github.com/settings/keys``` by creating ```New SSH key``` with all text in ```id_ed25519.pub```.<br/>
Now, one more step is to add the private key in local SSH agent, windows command prompt does not seem to support ```eval```, git bash can be used instead. <br/>
**Add the private key in local SSH agent**
```bash
eval $(ssh-agent -s) # start the ssh agent
ssh-add ~/.ssh/id_ed25519 # add the private key
```
Now you can clone the repo by SSH. <br/>
**Clone the repo by SSH**
```bash
git clone SSH_URL # clone the repo by SSH

$ Cloning into 'repo_name'...
$ This key is not known by any other names.
$ Are you sure you want to continue connecting (yes/no/[fingerprint])? #Type yes
```
<br/>
Once remote repository is cloned in local machine, there are several ways to communicate with the remote repo once there are new commits in the local. <br/>
**Exchange commits**
```bash
git push origin <branch_name> # push the commits to the remote repo
git push #if cloned branch, git will default to push to origin, which is short for remote repo
git pull # pull the commits from the remote repo
git fetch origin <branch> # fetch  particular branch from remote repo
git fetch # fetch all branches from remote repo
```

## Vscode Tutorial
Since VScode is the best editor on earth, hands down. It of course integrate git functionalities. Check the detailed official tutorial series from VScode for git. <br/>
{% include embed/youtube.html id='i_23KUAEtUM' %}


(TBC)

