# Objective
Setup multiple versions of python on the same machine
Allows for developing projects on multiple python versions

# Inspirations
- [pyenv - global and local versions](https://www.youtube.com/watch?v=3my06DUnApM)

# Setup 
1. `brew install pyenv` (MacOS)
1. 


# Common CommandsInstall
### - Install the latest python version
    `pyenv install $(pyenv install --list | grep -v - | grep -v b | grep -v dev | tail -1)`
    Installs only the latest stable version
    Excludes beta and dev versions
