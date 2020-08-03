# To create a new version of a package
First, locally and Gihtub:
 - clean your package (imports, comments, etc) and commit these changes
 - check that all the tests pass (activate venv and python -m unittest)
 - change the package version in the _version_ file
 - commit that change
 - tag that version in git with "git tag 0.X.0"
 - then push
 
Then, on pypi:
 - check that pip3 install wheel is installed
 - create and fill setup.py
 - create and fill MANIFEST.in
 - create and fill LICENSE
 - Re-create the wheels : python3 setup.py sdist bdist_wheel
 - check that twine is installed 
 - reupload the new package to test pypi first (skip-existing to avoid deleting old dist) :
 `python3 -m twine upload --repository-url https://test.pypi.org/legacy/ --skip-existing dist/*`
 - create a new venv and try to install with (does not install depedencies with `--no-deps`because other packages are not on TestPypi). The depedencies can be installed with `pip install -r requirements.txt)`: 
 `python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps physipy`
 - then upload on real pypi
 `python3 -m twine upload --skip-existing dist/*`
 - and test to install on a new venv from pypi
 
 
# Tests on on TestPypi : 
To upload on TestPypi
```
python3 -m twine upload --repository-url https://test.pypi.org/legacy/ dist/*
```
To install from TestPypi : in a venv : this will only install the package, not the dependencies (use pip install -r requirements.txt to install the dependencies from the real pypi). See (https://stackoverflow.com/questions/57151603/how-to-get-pypi-to-automatically-install-dependencies)[here as to why '--no-deps']:

```
python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps physipy
```

To open wheel file on mac : Open zip with password : `brew install p7zip` pour installer, puis `7za e archive.7z`


# setup.py
```python

with open('README.md', "r") as fh:
    long_description = fh.read()

setup(
    # the name that is used to "pip install" (not the name used to import physipy)
    name='physipy',
    # version of the PACKAGE on pypi, not necessarily of the code base (0.0.X means unstable) 
    version='0.0.1',
    #
    description="Hello",
    #### for a helloworld.py module in the src folder
    # actual python modules to include
    py_modules=["helloworld"],
    # and folder where to find the modules
    package_dir={"":"src"},
    
    
    ######### OPTIONNAL
    # classifiers pour recherche/indexage sur pypi
    classifiers=[
        "Programming Language :: Python :: 3",
    ],
    # long description, with the README.md file
    long_description=long_description,
    long_description_content_type="text/markdown",
    # pour avoir un mode d'installation spécial pour le dev par ex : pip install -e .[dev]
    extras_require = {
        "dev":[
            "pytest>=3.7",
        ]
    }
    url="path to github",
    author="author name",
    author_email="author email",

)
```
Optionnally, add a `README.md`file with :
```markdown
# Physipy

## Installation
Run `pip install physipy`

## Usage
```python
import physipy
```

then
```
python setup.py bdist_wheel
```
 
 
# More on setup : 
The  command `python3 setup.py sdist bdist_wheel` creates 2 installations : 
 - a tar.gz archive
 - a .whl archive : zip folder with formated filename
 
The tar.gz file is a source archive whereas the .whl file is a built distribution. Newer pip versions preferentially install built distributions, but will fall back to source archives if needed

In details : 

## sdist
- python3 setup.py sdist : creates 2 folders 
    - physipy.egg-info folder : with text files
    - dist folder with a file "physipy-0.2.0.tar.gz" containing 
```
physipy-0.2.0/
├── LICENSE
├── MANIFEST.in
├── PKG-INFO
├── README.md
├── physipy
│   ├── __init__.py
│   ├── _version.py
│   ├── constants.py
│   ├── custom_units.py
│   ├── quantity
│   │   ├── __init__.py
│   │   ├── calculus.py
│   │   ├── dimension.py
│   │   ├── plot.py
│   │   ├── quantity.py
│   │   ├── units.py
│   │   └── utils.py
│   └── quickstart.py
├── physipy.egg-info
│   ├── PKG-INFO
│   ├── SOURCES.txt
│   ├── dependency_links.txt
│   ├── requires.txt
│   └── top_level.txt
├── requirements.txt
├── setup.cfg
├── setup.py
└── test
    ├── test_dimension.py
    ├── test_physipy.py
    └── test_quantity.py
```


## bdist_wheel
creates 3 folders : 

- a physipy.egg-info folder : with text files
- a `build` folder, containing an empty folder called `bdist.macosx-10.11-x86_64` (temp folder used by the wheel) and a lib folder, that contains only the python code of the package :
```
build/lib/physipy/
├── __init__.py
├── _version.py
├── constants.py
├── custom_units.py
├── quantity
│   ├── __init__.py
│   ├── calculus.py
│   ├── dimension.py
│   ├── plot.py
│   ├── quantity.py
│   ├── units.py
│   └── utils.py
└── quickstart.py
```
- dist folder with a file "physipy-0.2.0-py3-none-any.whl"; it is a zip file with formated filename, containing : 


https://stackoverflow.com/questions/52700692/a-guide-for-updating-packages-on-pypi
https://stackoverflow.com/questions/51451966/twine-not-found-bash-twine-command-not-found


Ressources : 
 - https://www.youtube.com/watch?v=na0hQI5Ep5E
 - https://www.youtube.com/watch?v=zbNczZLP1tA
 - https://www.youtube.com/watch?v=02aAZ8u3wEQ
 - https://pyvideo.org/pycon-india-2019/python-packaging-where-we-are-and-where-were-headed-pradyun-gedam.html