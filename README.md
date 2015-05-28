# the-dump
A collection of useful commands, workflows, and information accumulated over the years coding and setting up experiments.

## Testing in Python
- http://pythontesting.net/framework/unittest/unittest-introduction/
  - Easy to follow introduction to unit testing in Python using the built-in `unittest` library.
- http://stackoverflow.com/a/129522
  - Test for thrown exceptions.

## Git

### Search the commit history for code snippets
[[source](http://stackoverflow.com/a/5816177)]
```
git log -S <code snippet> --source all 
git log -G <regexp> --source all # using regular expressions
```
- _use case_: searching for commits that affected a specific piece of code.

#### Sync a fork with an upstream repository

These git commands are assumed for the examples this section:
```bash
# Clone the repository to a local directory workspace.
git clone git@github.com:kianho/the-dump.git ./the-dump.git
# or if you prefer using HTTPS:
git clone https://github.com/kianho/the-dump.git ./the-dump.git
```

An _upstream_ repository typically refers to the original remote repository
from which a fork was created (into your github account). Assuming that you
have cloned a fork of this repository into ```./the-dump-fork```, you can run the following
commands to sync the state of this fork with the _upstream_ repository:
```bash
cd ./the-dump-fork

# Create a reference to the remote upstream repository, these are commonly
# named "upstream".
git remote add upstream git@github.com:kianho/the-dump.git

# (Optional) View the current list of remotes associated with this repository.
git remote -v

# Fetch/download all the upstream branches.
git fetch upstream

# Ensure that you are currently on the master branch.
git checkout master

# Merge any changes to upstream/master branch to the local master branch.
git merge upstream/master

# When you are ready, push changes in all local branches to the forked github repository.
git push --all
```

#### Viewing and accessing git history

```bash

# Revert a file to its last committed state.
git checkout -- <FILE>

# Revert a file to a specific version.
git checkout HEAD^ <FILE>  # previous version
git checkout HEAD~k <FILE> # k versions ago
git checkout HEAD@{k} <FILE> # a specific version

# Revert the entire repository to its last committed state.
git reset --hard

# View entire undo history of the repository
git reflog
git reflog <FILE> # for a single file.

# For example:
#   $ git reflog
#   a385a53 HEAD@{0}: commit: Added git history commands.
#   ac6e9f9 HEAD@{1}: commit: No longer using the git.md file.
#   5804748 HEAD@{2}: commit: Merged the git.md contents into README.md.
#   db2916d HEAD@{3}: pull --all: Fast-forward
#   5425ae2 HEAD@{4}: clone: from git@github.com:kianho/the-dump.git

```

#### git-flow
[git-flow](https://github.com/nvie/gitflow) is a suite of git extensions that enable
developers to conform to the [git branching workflow proposed by Vincent Driessen](http://nvie.com/posts/a-successful-git-branching-model/).

#### References
- http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes
- http://stackoverflow.com/a/7244456


## Anaconda & conda

### conda environments
```bash
# Create a new conda environment that uses python3.
# the "anaconda" component installs the default anaconda packages
conda create -n py3k python=3.4.2 anaconda

# ...and using python 2.7
conda create -n py27 python=2.7.8 anaconda

# Delete a conda environment (follow the subsequent prompts).
conda remove -n py27  --all

# Display all the conda environments (root is the default).
conda info -e

# Activate the py3k environment.
source activate py3k

# ... the py3k environment is now active (see below to deactivate it).

# Deactivate the py3k environment.
source deactivate
```
