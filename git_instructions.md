# Instructions

- [Instructions](#instructions)
  - [Settings for SSH](#settings-for-ssh)
  - [Initiate a repository](#initiate-a-repository)
  - [Clone the repository with HTTPS](#clone-the-repository-with-https)
  - [Go to the repo folder directory](#go-to-the-repo-folder-directory)
  - [See all changes in the repository](#see-all-changes-in-the-repository)
  - [Before you commit](#before-you-commit)
  - [Now commit you file!](#now-commit-you-file)
  - [Push commited files to a remote repository](#push-commited-files-to-a-remote-repository)
  - [Create .gitignore](#create-gitignore)
  - [Remove files](#remove-files)
  - [Revert deleted files](#revert-deleted-files)
  - [Branching](#branching)
  - [See changes](#see-changes)
  - [Pull requests](#pull-requests)
  - [Update changes in the remote repository to local](#update-changes-in-the-remote-repository-to-local)
  - [Merge branches](#merge-branches)
  - [Update with changes in the master branch](#update-with-changes-in-the-master-branch)
  - [After the merge, delete the branch](#after-the-merge-delete-the-branch)
  - [Log of all commits](#log-of-all-commits)
  - [Undoing shit](#undoing-shit)

## Settings for SSH
```
ssh-keygen -t rsa -b 4096 -C "email@test.com"
```
Set a name and password for the key files.

Look at your files:
```
ls
```
There will be 2 files:
- yourkeyame: your private key (don't share)
- yourkeyname.pub: you public key

Making sure that the git knows that key
Ensure the ssh-agent is running

```
eval "$(ssh-agent -s)"
``` 
## Initiate a repository
```
git init
```

Create an empty repository on github.

And then connect
```
git remote add origin https://github.com/ericyaang/git-instructions.git
```
Check the connection
```
git remote add origin https://github.com/ericyaang/git-instructions.git
```
Push!
```
git push origin master
```


## Clone the repository with HTTPS

```
git clone https://github.com/user-name/repo-name.git

```

## Go to the repo folder directory
```
cd repo-name
```

## See all changes in the repository
```
 ls -la
```

## Before you commit

This command will show you all the changes that have not been committed yet.
```
git status
```
If the file is untracked, this means that you need to add the file to git before anything else.
```
git add file
```

or use . to track all files.
```
git add .
```
## Now commit you file!
```
git commit -m "what and why" -m "some description"
```

## Push commited files to a remote repository

`origin` is the location of the repository.
`master` is the branch that we want to push.
```
git push origin master
```

Lazy push:
```
git push -u origin master
```
then just type use: `git push`

## Create .gitignore
```
touch .gitignore
```

## Remove files
```
git rm file.txt
```
Remove only from repository
```
git rm --cached file.txt
```

## Revert deleted files
```
git reset --hard HEAD
```

## Branching

See what is there
```
git branch
```

Switch between branches
```
git checkout branch-name
```

Create a new one
```
git checkout -b name-of-the-branch
```

## See changes
```
git diff name-of-the-branch
```

## Pull requests

A request to have your code pulled in another branch

Create request pull to the master branch

```
git push origin branch-name
```
## Update changes in the remote repository to local

```
git pull
```
## Merge branches
Remember to checkout
```
git diff master
git merge master
```
## Update with changes in the master branch
```
git diff master
git commit -am "updated with master"
```
## After the merge, delete the branch
```
git branch -d name-of-the-branch
```

## Log of all commits
```
git log
```

## Undoing shit

Staged
```
git reset name.py
```
Commits
```
git reset HEAD
```
Vorletzte commit
```
git reset HEAD~1
```
For multiple commits, check log and copy the hash of the commit and then
`--hard` to remove all changes
```
git reset --hard c2119af9239eaf762e7e84a7a4859d42f8665660
```