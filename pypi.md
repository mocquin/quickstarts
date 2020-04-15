# To create a new version of a package
First, locally and Gihtub:
 - clean your package (imports, comments, etc) and commit these changes
 - check that all the tests pass
 - change the package version in the _version_ file
 - commit that change
 - tag that version in git with "git tag version 0.X.0"
 - then push
 
Then, on pypi:
 - check that pip3 install wheel is installed
 - Re-create the wheels : python3 setup.py sdist bdist_wheel
 - check that twine is installed 
 - reupload the new package (skip-existing to avoid deleting old dist) : python3 -m twine upload --skip-existing dist/* 
 
 
# Tests on on TestPypi : 
To upload on TestPypi
```
python3 -m twine upload --repository-url https://test.pypi.org/legacy/ dist/*
```
To install from TestPypi : in a venv : 

```
python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps physipy
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
