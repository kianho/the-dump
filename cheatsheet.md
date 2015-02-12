# Git
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

### Further reading
- http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes
