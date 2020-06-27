# Package

To create a package, the directory with the scripts to be imported must contain a file named `__init__.py`. The file can be empty, the directory just needs to have a file with this name.

You can add some "shortcuts" in the `__init__.py`. For example, given a directory named `distributions` with file `Gaussiandistribution.py` and `Generaldistribution.py` you can add this line in the `__init__.py` file:
`from .Gaussiandistribution import Gaussian`

This allows one to import the `Gaussian` class directly in any file that uses this package using `from distributions import Gaussian`.

The `setup.py` file is necessary for pip installing and should be located at the same level as the directory for your package:
```
├── distributions
│   ├── Gaussiandistribution.py
│   ├── Generaldistribution.py
│   └── __init__.py
└── setup.py
```

The `setup.py` file contains:
```
from setuptools import setup

setup(name='distributions',
        version='0.1',
        description='Gaussian distributions',
        packages=['distributions'],
        zip_safe=False)
```

You can install your package by going to the directory with the `setup.py` file and then type `pip install .` to install the package. This installs the package whereever pip is configured to install packages on your system. From the Python interpreter you can import the package, e.g. `import distributions` and then type this to see where it was installed, `distributions.__file__`.



NOTE: The import syntax is different between Python 2 and Python 3.