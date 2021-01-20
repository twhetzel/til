# PyPI


Anyone can upload a package to PyPI and anyone can use your package if it's on the regular PyPI. There is a test repository (https://test.pypi.org/) and a the regular (https://pypi.org/).

You'll need an account on PyPI in order to upload your package. Other files to include in your package are:
- `license.txt` - add license text
- `README.md` - document how the package works
- `setup.cfg` - add the name of the README file in this file


Every package pn PyPI needs a unique name. In the `setup.py` file use the same name for name and packages variables.




Example
```
cd binomial_package_files
python setup.py sdist
pip install twine

# commands to upload to the pypi test repository
twine upload --repository-url https://test.pypi.org/legacy/ dist/*

# install package from the test repository
pip install --index-url https://test.pypi.org/simple/ dsnd-probability


# command to upload to the pypi repository
twine upload dist/*
pip install dsnd-probability
```


