#### Getting Started
```bash
# Create empty Git repo in specified directory
git init

# Clone (download) a repository that already exists on GitHub/BitBucket/GitLab
#including all of the files, branches, and commits
git clone <git-url>
```

#### Configuration
```bash
# Configure user information for all local repositories

# Enables helpful colorization of command line output
git config --global color.ui true

# Sets the name you want attached to your commit transactions
git config --global user.name <"Your Name">
# Sets the name you want attached to your commit transactions
git config --global user.email <your email>
```

#### Branching
```bash
# See the list of all local branches
git branch

# Switch to existing local branch
git checkout <branchname>

# Checkout current branch into a new branch, named new-branch-name
git checkout -b <new-branch-name>

# Merge branch-name into the current branch
git merge <branchname>

# Soft branch delete, will complain if the branch is not merged
git branch -d <branchname>

# Hard branch delete, will not complain about nothing. Like rm -rf in bash
git branch -D <branchname>
```

#### Updating Current Branch

```bash
# See status of your current git branch.
git status

# Short view of status. Helpful for seeing things at a glance
git status -s

# Add modified file to be commited(aka stage the file)
git add <filename>

# Add all modified files to be commited(aka stage all files)
git add .

# Add only text files, etc.
git add '*.txt'

# Tell git not to track file anymore
git rm <filename>

# Record changes to git. Default editor will open for a commit message.
# A short hand for commiting files and writing a commit message via one command
git commit -m 'Some commit message'

# Changing the previous commit, if you haven't pushed it yet to a remote repo
# Simply make new changes, add them via git add, and run the following command.
# Past commit will be ammended.
git commit --amend

# See all commits
git log

# Pretty commit view, you can customize it as much as you want.
git log --pretty=format:"%h %s" --graph

# See what you worked on in the past week
git log --author='Alex' --after={1.week.ago} --pretty=oneline --abbrev-commit

# See only changes made on this branch (assuming it was branched form master branch)
git log --no-merges master..
```

#### Redo commits
```bash
# Unstage pending changes, the changes will still remain on file system
git reset

# Unstage pending changes, and reset files to pre-commit state. If
git reset --hard HEAD

# Go back to some time in history, on the current branch
git reset tag
git reset <commit-hash>
```

#### Staging
```bash
# Save current changes, without having to commit them to repo
git stash

# And later return those changes
git stash pop

# Return file to it's previous version, if it hasn’t been staged yet.
# Otherwise use git reset filename or git reset --hard filename
git checkout <filename>
```


#### Comparing difference
```bash
# See current changes, that have not been staged yet.
git diff

# See current changes, that have not been commited yet (including staged changes)
git diff HEAD

# Compare current branch to some other branch
git diff <branch-name>

# Same as diff, but opens changes via difftool that you have configured
# -d tells it to open it in a directory mode, instead of having to open
# each file one at a time.
git difftool -d

# See only changes made in the current branch (compared to master branch)
# Helpful when working on a stand alone branch for a while
git difftool -d master..

# See only the file names that has changed in current branch
git diff --no-commit-id --name-only --no-merges origin/master...

#Your diff condition
git diff --stat 
```

#### Working with Remote Branch

```bash
# See list of remote repos available. If you did git clone,
git remote

# Detailed view of remote repos, with their git urls
git remote -v

# Add a new remote. I.e. origin if it is not set
git remote add origin <https://some-git-remote-url>

# Push current branch to remote branch called upstream branch
git push

# If a remote branch is not set up as an upstream, you can make it so
# The -u tells Git to remember the parameters
git push -u origin master

# Otherwise you can manually specify remote and branch to use every time
git push origin branchname

# Just like pushing, you can get the latest updates from remote.
# By defaul Git will try to pull from "origin" and upstream branch
git pull

# Or you can tell git to pull a specific branch
git pull origin <branchname>

# Git pull, is actually a short hand for two command.
# Telling git to first fetch changes from a remote branch
# And then to merge them into current branch
git fetch && git merge origin/remote-branch-name

# If you want to update history of remote branches, you can fetch and purge
git fetch -p

# To see the list of remote branches
git branch -a
```