# Virtual Environment

A virtual environment provides a "space" away from your main Python installation to
install packages without affecting your main Python installation.

A virtual environment can be set-up with `conda` or `venv`.

## Conda
 Conda does two things: manages packages and manages environments.

As a package manager, conda makes it easy to install Python packages especially for data science. For instance, typing conda install numpy will install the numpy package.

As an environment manager, conda allows you to create silo-ed Python installations. With an environment manager, you can install packages on your computer without affecting your main Python installation.

The command line code looks something like this:
```
conda create --name environmentname
source activate environmentname
conda install numpy
```


## Pip and Venv

 venv is an environment manager that comes pre-installed with Python 3. Pip is a package manager.

Pip can only manage Python packages whereas conda is a language agnostic package manager. In fact, conda was invented because pip could not handle data science packages that depended on libraries outside of Python.

Conda manages environments AND packages. Pip only manages packages.

To use venv and pip, the commands look something like this:
```
python3 -m venv environmentname
source environmentname/bin/activate
pip install numpy
```


## Which to choose?
Whether you choose to create environments with venv or conda will depend on your use case. Conda is very helpful for data science projects, but conda can make generic Python software development a bit more confusing; that's the case for this project.

If you create a conda environment, activate the environment, and then pip install the distributions package, you'll find that the system installs your package globally rather than in your local conda environment. However, if you create the conda environment and install pip simultaneously, you'll find that pip behaves as expected installing packages into your local environment:

```
conda create --name environmentname pip
```

On the other hand, using pip with venv works as expected. Pip and venv tend to be used for generic software development projects including web development. For this lesson on creating packages, you can use conda or venv if you want to develop locally on your computer and install your package.



## Instructions for venv
[Python documentation](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/)

```
python3 -m venv env
source env/bin/activate
```
In this case, `env` is the name of the virtual environment, you can use whatever name you want.

When done with the virtual environment run `deactiavte` to leave the virtual environment.

If you no longer want the virtual environment, you can simply delete the virtual environment folder.





