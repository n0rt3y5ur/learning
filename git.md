# learning-git
Commands and tips to get the ropes

## Install

From: https://git-scm.com/

## Git basic commands

Go to your prooject folder and, then, initialize a repo with
```
git init
```
Once you do that, you will see a .git folder in your project folder.

### git status
This tells you what it is not still saved in the repository. These are the "untrack" files.
```
git status
```

### git add
"Git add" add changed files/folders to the repository staging area of the branch. It tracks them. You can add a single file with:
```
git add <file>
```
You can also add a folder

```
git add <folder>
```
You can add all unstageg files with a dot: 

```
git add .
```

### git rm --cached
You can unstage files from being commited
```
git rm --cached <file>
```

### git commit
Commit the changes you have staged properly with:
```
git commit -m "message that describes what you have changed"
```

### git branch
To create a new branch:
```
git branch <newBranchName>
```

To list all existing branches:
```
git branch
```

To switch to a branch:
```
git checkout <destinationBranch>
```

To create a new branch and checkout into it in one command:
```
git checkout -b <branchName>
```
To delete a branch:
```
git branch <branchName> -d
```
If you want to force the deletion (maybe some changes are not staged), then:
```
git branch <branchName> -D
```

### git merge
Having two branches (main and newbranch), to merge changes contained in newbranch to main branch, go to main branch with "git checkout main" and merge the new branch with:
```
git merge <newBranch>
```

### git log
It displays all commits and their commit message. Every commit has an id associated. Yo can use that id for reverting changes.
```
git log
```

### git revert
Ít allows us to revert back to a previous version of our project.
```
git revert <commitId>
```

### .gitignore
It's a configuration file that allows you to hide existing files and folders in your repository. Content listed there don't get pushed to a public repository. The file is called .gitignore and has one line per resource to be ignored.

Also, important,  if a file was staged before you will need to remove it from cache...

### git remove --cached
To remove from cached files and include it later into the .gitignore file list.
```
git remove --cache <fileName>
```

### git remote 
To connect my local project folder to the github repo.
```
git remote add origin https://github.com/norteysur/learning.git
```
Note to consider: the url of my empty repo was "https://github.com/norteysur/learning". In the command we are adding ".git"

### git push
To push our local changes into the connected github repo:
```
git push -u origin main
```
Note: origin references the connection, and main is because we are in the main branch (that's what we are pushing).

### Some tricks

#### Counting commits
```
git rev-list --count
```
If you want to specify a branch name:
```
git rev-list --count <branch>
```

#### Backing-up untracked files
Git, along with some Bash command piping, makes it easy to create a zip archive for your untracked files.
```
$ git ls-files --others --exclude-standard -z |\
xargs -0 tar rvf ~/backup-untracked.zip
```

#### Viewing a file of another branch
Sometimes you want to view the content of the file from another branch. It's possible with a simple Git command, and without actually switching your branch.

Suppose you have a file called README.md, and it's in the main branch. You're working on a branch called dev: git show main:README.md
```
git show <branchName>:<fileName>
```
