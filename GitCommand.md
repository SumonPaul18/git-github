# Git Command Using

### Add global user/mail:

    git config --global user.name "Sumon Paul"
    git config --global user.mail "sumonpaul267@gmail.com"

### Add local user/mail:

    git config --local user.name "Your Name Here"
    git config --local user.email "your_email@youremail.com"

### Show config list:

    git config --list

### Check branch:

    git branch

### create a new repository on the command line:
    git init
####    
    git add  --all / specefic file 	- add for Staging area
####
    git commit -m "first commit"
####
    git branch -M main
####
    git remote add origin https://github.com/SumonPaul18/SumonPortfolio.git
####
    git remote show origin
####
    git push -u origin main

### Create new branch:

    git checkout -b [new branch name]

### Switch branch:

    git checkout [brunch-name]

### Do for merge (master to others)

    git merge <branch-name>

### Show commit log
git log			- show commit log shortly
git log --patch		- show commit log details
git log --oneline		- show only commit message
git show [commit code]	- git show 6bab78a

### Clone a Specific Git Branch Repository

git clone --single-branch --branch <b>BranchName</b> <b>RepoUrl</b>

    git clone --single-branch --branch easylinux-v.1 https://github.com/SumonPaul18/easylinux.git






