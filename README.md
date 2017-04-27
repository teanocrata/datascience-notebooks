# datascience-notebooks
Some examples of data science notebooks with Jupyter Notebook Data Science Stack

## How to use this notebooks

You need to have anaconda platform installed. You can download it from his download page. The notebooks has been tested with Python 3.4 version.

From the root folder of the project:
```bash
$ jupyter notebook
```

This starts the notebook server from the command line, will print some information about the notebook server in your terminal, including the URL of the web application.

You will see the notebook dashboard which will show a list of the notebooks, files and subdirectories in the root folder of the project.

## Using environments

In order to have clean and separate environments you need to create an environment for the project.

In order to have clean and separate environments, we have used conda enviroments and you can create your own environment for the project ussing the environments files like `twitter-example-environment.yml`:

```bash
$ conda env create -f twitter-example-environment.yml
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
(twitter-example)$ source deactivate
```
*   Windows
```bash
(twitter-example)$ deactivate
```

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


## Twiter inference example

The Question: What is the probability that a tweet originating from within Colombia contains at least 1 occurence of the word "yo" with any given composition of accents, and capital and lowercase letters?

### Requirements

PostgreSQL with one 'twitter_inference' database
Bokeh server
Twitter keys propertly configured: you can follow [Conda - Saved environment variables](https://conda.io/docs/using/envs.html#saved-environment-variables) to store the secret keys:
```
TWITTER_CONSUMER_KEY='Your Twitter Consumer Key (API Key)'
TWITTER_CONSUMER_SECRET='Your Twitter Consumer Secret (API Secret)'
TWITTER_ACCESS_TOKEN='Your Twitter access token'
TWITTER_ACCESS_TOKEN_SECRET='Yout Twitter Access Token Secret'
```
You can get it at [Twitter application Management](https://apps.twitter.com)

#### With docker

```bash
$ docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 -d postgres
$ docker run --name some-pgadmin4 --link some-postgres:postgres -p 5050:5050 -d fenglc/pgadmin4
```

### Step by Step

1.  At <http://[pgadmin4-host]:5050> connect to the PostgreSQL and create a new database named 'twitter_inference'
1.  At <http://[pgadmin4-host]:5050> create a new table 'tweets' in 'twitter_inference' database:
    ```sql
    -- Table: public.tweets

    -- DROP TABLE public.tweets;

    CREATE TABLE public.tweets
    (
        id_str character varying(50) COLLATE pg_catalog."default",
        text character varying(200) COLLATE pg_catalog."default"
    )
    WITH (
        OIDS = FALSE
    )
    TABLESPACE pg_default;

    ALTER TABLE public.tweets
        OWNER to postgres;
    ```
1.  Start bokeh server
    1.  Open a new terminal and activate the environment
    ```bash
    $ activate twitter-example
    (twitter-example)$ bokeh serve
    ```
1.  Execute cells on twitter-inference-production from Jupyter notebook, last cell open a session to keep our local document in sync with server.

## Insults prediction example

Machine learning model to detect insults in social networks. From [Detecting Insults in Social Commentary at kaggle](https://www.kaggle.com/c/detecting-insults-in-social-commentary)

The challenge is to detect when a comment from a conversation would be considered insulting to another participant in the conversation. Samples could be drawn from conversation streams like news commenting sites, magazine comments, message boards, blogs, text messages, etc.

The idea is to create a generalizable single-class classifier which could operate in a near real-time mode, scrubbing the filth of the internet away in one pass.

## Bayesian A/B test

Classic A/B Test, we generate data with a probability and we try to find later these probability.
