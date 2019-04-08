# What it is

`p3` is a very simple commandline front-end for me to handle different python3 virtual environments.

Typical tasks like

* Setign up an environment from a `requirements.txt` and some `sources`
* Updating/installing python packages
* Actually packaging all into one big shell file that can run anywhere the same architecture and of course `python3-venv` must be available

# Installation

## Requirements

Your system must have the `python3-venv` module.

## Script Installation

Fairly simple:

    cd /usr/local/bin # or wherever you want to have it
    curl -O https://raw.githubusercontent.com/turbobert/p3/master/src/p3
    chmod a+x p3

The script actually does *not* need `root`privileges.

# Usage

    # create an empty directory
    mkdir $HOME/src/my-app

    # initialize
    ( cd $HOME/src/my-app; p3 init )

    # install requests for example
    ( cd $HOME/src/my-app; p3 i requests )

    # copy your main-python file to exactly that following location:
    # no need for chmod a+x
    cp PYTHONFILE $HOME/src/my-app/src/main.py

    # to build/compile:
    ( cd $HOME/src/my-app; p3 c )

    # run it:
    $HOME/src/my-app/my-app
    