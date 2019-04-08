# What it is

`p3` is a very simple commandline front-end for me to handle different python3 virtual environments.

Typical tasks like

* Setting up an python environment from `requirements.txt` and your `sources`
* Updating/installing python packages in that env
* Actually freezing it all together in one binary
  * This is one big Bash script
  * That can run anywhere the same architecture
  * Only dependency is `python3-venv` (including python)

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

    # put this binary where ever you want on the same architecture
    # so you can't cross "compile" this (I know this is not actually
    # compiling python)

# How it works

When you actually execute the binary generated, it will just extract itself (a tarball with python3 env and your code) somewhere into /tmp and execute then with the parameters given to the original bash file your `main.py`. The one special thing that happens is a path replacement in the python environment, the path there is hard coded from your initial installation.

# Supported Platforms

I use this under:

* Debian Linux (Stable, currently 2019)
* MacOS (latest)
* Raspbian Linux
