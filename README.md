# data-science-advanced
Deeper into Data Science

## How to use this notebooks

You need to have anaconda platform installed. You can download it from his download page. The notebooks has been tested with Python 3.4 version.

From the root folder of the project:
```bash
$ jupyter notebook
```

This starts the notebook server from the command line, will print some information about the notebook server in your terminal, including the URL of the web application.

You will see the notebook dashboard which will show a list of the notebooks, files and subdirectories in the root folder of the project.

## Using environments

In order to have clean and separate environments, we have used conda enviroments and you can create your own environment for the project ussing the environment file `environment.yml`:

```bash
$ conda env create -f environment.yml
```

Activate the new environment to use it:
*   Linux, Mac
```bash
$ source activate ./twitter-example
```
*   Windows
```bash
$ activate .\twitter-example
```

Deactivate the current environment
*   Linux, Mac
```bash
$ source deactivate
```
*   Windows
```bash
$ deactivate
```
