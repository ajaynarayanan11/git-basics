# Git commands

## Setup and startup

*To initialize the selected folder as git working directory*
    
    git init 

Shows status of working tree
git status

# Adding files to staging area (index file)

git add <file> : To add file to staging area
git add . : To add all files in the directory to staging area

# Create user config before commiting files

git config --global user.email "ajaynarayanan11@gmail.com"
git config --global user.name "AjayN"

git config --global --list

# Commiting files (Adding files to object folder, or saving)
git commit -m "<message>" : Saves all the staged files(files that are being tracked in the index area)
git commit -a -m "" : Adds files to staging area if not already added and then commits the change

# Git logs
git log : to view commit history. (q to exit)
git show : to see details about a specific commit, including what changes were made.
git reflog :  Shows all activity of the head with its hash value in the current working branch

# Checkout / branching

git checkout <commit id> : switches to the branch at that time of commit
git checkout master : switches back to master branch
git branch : To list all the branches
git branch <branch-name> :  To create new branch
git branch -b <branch-name> : Create new branch and switch to that branch

# Merging a branch to another

git checkout <target branch> : Switch to target branch to which it be merged
git merge <branch-name> : Name of the branch to be merged


# Deleting files

git ls-files : To list the files present in staging area
git rm <file-name> :  To remove file from direcory and staging area

# To revert the changes in staged files which was not commited

git checkout <file-name> | git restore <file>: To revert specific file
git checkout . | git restore . : To revert all the changes in file to last commit

git restore : if file was staged already then  do 'git checkout'

# Git cleanup

git clean -dn : Shows Cleans up details
git clean -df :  Force cleanup without showing details

# Git reset

git reset --soft HEAD~1 : Soft resetting current branch head back to one last commit

# Deleting branches

git branch -d <branches name space seperated>: Only allows removal of branch if that branch is already merged to master
git branch -D <branches name space seperated>: Force delete even if it is not merged

# Detatched head

Detatched Head : When you go to a specific previous commit id, head becomes a detached head
To save the changes if switching to a different branch, create branch with that detatched head id and then merge

# Git Ignore

To ignore any file / that need not to be tracked by git, create .gitignore file and add the list of files to be ignored inside of it
*.pdf :  Ignores all files with pdf format
web-app/* : Ignores all files in the the folder including folder

# Working with remote repository

git remote add origin https://github.com/ajaynarayanan11/git-basics.git
git branch -M main                                                      # If want to rename the master to main
git push -u origin main /  git push origin master


## =======================================
## Workflow of tracking an own new project
## =======================================

1. Create a Git Repository
--------------------------
#Initialize a new Git repository:
git init

#Clone an existing repository:
git clone <repository-url>

2. Set Up Your Identity
-----------------------
# Configure your username and email (if not already set):
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

3. Create and Manage Files
---------------------------
# Check the status of your repository:
git status

# Add files to the staging area:
git add <file-name>  # For a specific file
git add .            # For all changes

# Remove files from the staging area:
git reset <file-name>

4. Committing Changes
---------------------
# Commit your changes:
git commit -m "Your commit message"

5. Branching and Merging
------------------------
# Create a new branch:
git checkout -b <branch-name>

# Switch to an existing branch:
git checkout <branch-name>

# Merge a branch into the current branch:
git merge <branch-name>

# Delete a branch:
git branch -d <branch-name>

6. Remote Repository Management
-------------------------------
# Add a remote repository:
git remote add origin <repository-url>

# Pull changes from a remote repository (suppose there are some readme files in ur new repo):
git pull origin <branch-name>

# Push changes to a remote repository:
git push origin <branch-name>

# Fetch changes from a remote repository:
git fetch origin

7. Viewing History and Differences
----------------------------------
# To see commit log
git log

# To See last commit
git log -1

#View differences between commits:
git diff <commit-id1> <commit-id2>

8. Tagging Releases
-------------------
# Create a new tag:
git tag -a v1.0 -m "Version 1.0"

#Push tags to remote:
git push origin --tags

9. Cleaning Up
---------------
# Remove untracked files:
git clean -f

#Reset to a previous commit (WARNING: This can lose changes):
git reset --hard <commit-id>

10. End of Project
------------------
# Archive the repository (optional):
You can create a zip of the repository or simply leave it as is.

# Delete the local repository (optional):
rm -rf <repository-folder>