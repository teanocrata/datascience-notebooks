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
*   Linux, Mac ```$ source activate ./py34```
*   Windows ```$ activate .\py34```

Deactivate the current environment
*   Linux, Mac ```$ source deactivate```
*   Windows ```$ deactivate```

## Using gmaps for map visualization

Make sure that you have enabled widgets extensions to Jupyter:
```
$ jupyter nbextension enable --py --sys-prefix widgetsnbextension
```
Install the Python component using:
```
$ pip install gmaps
```
Then tell Jupyter to load the extension with:
```
$ jupyter nbextension enable --py gmaps
```

## With docker

```
$ docker run -it --rm -p 8888:8888 -v $(pwd):/home/jovyan/work jupyter/datascience-notebook
```
