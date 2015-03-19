# the-dump
A collection of useful commands, workflows, and information accumulated over the years coding and setting up experiments.

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
