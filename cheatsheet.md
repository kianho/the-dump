# Git
These git commands are assumed for the examples this section:
```bash
# Clone the repository to a local directory workspace.
git clone git@github.com:kianho/cheatsheets.git ./cheatsheets
# or if you prefer using HTTPS:
git clone https://github.com/kianho/cheatsheets.git ./cheatsheets
```
## Sync a fork with an upstream repository
An _upstream_ repository typically refers to the original remote repository
from which a fork was created (into your github account). Assuming that you
have cloned a fork of this repository into ```./cheatsheets-fork```, you can run the following
commands to sync the state of this fork with the _upstream_ repository:
```bash
cd ./cheatsheets-fork

# Create a reference to the remote upstream repository, these are commonly
# named "upstream".
git remote add upstream git@github.com:kianho/cheatsheets.git

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

## git-flow
[git-flow](https://github.com/nvie/gitflow) is a suite of git extensions that enable
developers to conform to the [git branching workflow proposed by Vincent Driessen](http://nvie.com/posts/a-successful-git-branching-model/).

## References
- http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes
- http://stackoverflow.com/a/7244456

# Anaconda & conda
## conda environments
```bash
# Create a new conda environment that uses python3.
conda create -n py3k python=3.4.2

# Display all the conda environments (root is the default).
conda info -e

# Activate the py3k environment.
source activate py3k

# Activate the root environment.
source activate root
```
