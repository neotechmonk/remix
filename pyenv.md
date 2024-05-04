# Objective
Setup multiple versions of python on the same machine
Allows for developing projects on multiple python versions

# Inspirations
- [pyenv - global and local versions](https://www.youtube.com/watch?v=3my06DUnApM)
- [description on additional commands](https://realpython.com/intro-to-pyenv/)


# Setup 
1. Install on MacOS - `brew install pyenv` 
1. Install new python version - `pyenv install -v 3.7.2`
    exclude -v to suppress tail
1. Check currently installed versions `pyenv versions`
    Currently active version is prefixed with *
1. Use a specific version globally `pyenv global 3.7.2`
1. Use a specific versionally locally (e.g. specific project folder) `pyenv local 3.7.2`
    adds `.python-version` in the local folder
1. Verify the active version `python -V`
1. Uninstall a version `pyenv uninstall -f 3.7.2`
    Avoid -f to allow system to prompt confirmation



# Common CommandsInstall
### - Install the latest python version
    `pyenv install $(pyenv install --list | grep -v - | grep -v b | grep -v dev | tail -1)`
    
    Installs only the latest stable version
    Excludes beta and dev versions

### - Get list of python versions available
    `pyenv install --list | grep " 3\.[678]"`
    E.g. between 3.6 - 3.8 all releases including dev

### - Inspect installed versions
    `ls ~/.pyenv/versions/`
    Folder related to specific version is auto deleted on 
    `pyenv uninstall`

### - Setting up a `.venv` with `poetry`
    First `pyenv local x.x.x` if a specific version needs to be activated
    Then run `poetry init` to use the local python version in the .venv

    Sometimes the specific version would not be used for initiated
    Use a relaxed version of python instead. E.g. ^3.8

    Also try `poetry env use 3.8.19`
