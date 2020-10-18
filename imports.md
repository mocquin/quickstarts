# A comprehensive quick-tutorial on how imports work in Python

 
## What is accessible : `sys.path`
When calling `import numpy`, python will look through all the folders in the PYTHON PATH, for any folder called `numpy`, or any file called `numpy.py`. If it is not in the path, it can't be imported.

To know what is the PYTHON PATH, simply use :
```python
import sys
print(sys.path)
```
The folder where the file using `import` is called is also added to the PYTHON PATH.

According to the doc, the `path` variable contains : 
 - in path[0] : 
  - if python used as `python path/to/file`, the directory containing the script that was used to invoke the Python interpreter, ie `'path/to/file'` --> so when calling a script, the location from where it was called doesn't matter
  - if python was used as `python`, contains empty string `''`, and python will look inside the directory where `python` was called
 - then the content of PYTHONPATH: list of paths to folders sepated by os.pathsep
 

## PATH

use the full path `/.../.../python`will always work

### On windows: 
the environement varibale PATH : list of directories the console looks in to find commands (the `python.exe` file must be in one of the folder in the PATH list so that `python` works)

### On mac/linux
`which python` to locate what python the `python`command will launch
`type python`
`echo $PATH$`


#### mac
`
cd
vim .bash_profile
`
append : `export PYTHONPATH="/Users/toto/modulepy`
then `source ~/.bash_profile` or restart terminal


#### linux
`
cd
vim .bash_rc
`

one-time
`
alias python=python3
`
always : put in bash_profile
`
alias python=python3
alias pip=pip3
`

`pip show numpy`


## python executable and version
```python
print(sys.version)
print(sys.executable)
```

## modify the path with code
```python 
import sys
>>> sys.path.insert(0, "/home/olivier/scripts")
```



# In python

## Do's and Dont's of `import` 
The `import`expects a **MODULE** or a **PACKAGE**.

Do's : 
 - `import module`
 - `import package`
 - `import package.module`
 - `import package.subpackage.module`

Dont's:
 - `import module.var`
 - `import package.module.var`
 - `import package.subpackage.module.var`
 
## Do's and Dont's of `from ... import ...`
 
Do's : 
 - `from module import var`
 - `from package import subpackage`
 - `from package.subpackage import module`
 - `from package.subpackage.module import var`
 - `from package import var_in_init_file`
 
Dont's : 
 - None !


## PYTHON PATH
```python
import os
os.environ['PYTHONPATH']
```

## path to modules/package
Any imported module/package can be located with it's `__file__`attribute

```python
import numpy
numpy.__file__
> "/opt/anaconda3/lib/python3.7/site-packages/numpy/__init__.py"
```
## timing imports
In CLI : `python -X importttime myscript.py`
To visualiaze results :
`pip install tuna`
`python -X importttime myscript.py 2> import.log`
`tuna import.log`



# Ressources
https://chrisyeh96.github.io/2017/08/08/definitive-guide-python-imports.html
https://bic-berkeley.github.io/psych-214-fall-2016/using_pythonpath.html