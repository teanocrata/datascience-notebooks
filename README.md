# datascience-notebooks
Some examples of data science notebooks with Jupyter Notebook Data Science Stack

## How to use this notebooks

You need to have anaconda platform installed.

You can download it from his download page.

The notebooks has been tested with Python 3.6 version.

Next, simply execute ```jupyter notebook``` from the root folder of the project.

This starts the notebook server from the command line, will print some information about the notebook server in your terminal, including the URL of the web application.

You will see the notebook dashboard which will show a list of the notebooks, files and subdirectories in the root folder of the project.

## Using environments

In order to have clean and separate environments you need to create an environment for the project.

Create an environment named py34 in the current folder:
```
$ conda create --prefix py34 python=3.4
```

Activate the new environment to use it:
LINUX, MAC ```$ source activate ./py34```
WINDOWS ```$ activate .\py34```

Deactivate the current environment
LINUX, MAC ```$ source deactivate```
WINDOWS ```$ deactivate```
