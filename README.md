# What it is

`p3` is a very simple commandline front-end for me to handle different python3 virtual environments.

Typical tasks like

* Setup an environment form a `requirements.txt` and some source files
* updateing/installing python packages
* actually packaging all into one big shell file that can run anywhere the same architecture and of course `python3-venv` must be available

# Installation

## Requirements

Your system must have the `python3-venv` module.

## Script Installation

Fairly simple:

    cd /usr/local/bin # or wherever you want to have it
    curl -O https://raw.githubusercontent.com/turbobert/p3/master/src/p3
    chmod a+x p3

The script actually does *not* need `root`privileges.
