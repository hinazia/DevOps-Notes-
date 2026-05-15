
# GIT COMMANDS

## Setup and Config

    git --version
    git config ----> shows the configuration

## Setting Name and Email Globally

    git config --global user.name "Hina Qazi"
    git config --global user.email <email address>

## Basic Worflow

    git add   -----> File Status from Untracked to Staged
    git commit ----> File Status from Staged to Tracked
    git rm <dir/file_name> -----> to delete file
    git rm --cached <file> -----> tell git to forget file without deleting it
    git push origin main ---> local to remote
    git pull origin main ---> remote to local
    git clone <url> --------> clone an existing repo

## Viewing Changes

    git status ----> check what you added
    git log    ----> View the commit History

## Branching

    git branch ----> List all branches in a repo
    git branch -d <name>              -----> to delete a branch
    git checkout -b <branch_name>     ----> creates a new branch with the commit history of the parent branch
                                            and also directly switches to it
    git switch/checkout <branch_name> ----> switches between branches


    
     
