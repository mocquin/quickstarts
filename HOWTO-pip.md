
# Quickstart
```
pip help
pip install numpy==1.0
pip show numpy
pip install --upgrade numpy
pip install --upgrade numpy --verbose
pip uninstall numpy
pip list
pip list --outdated
pip freeze > reqs.txt
pip --version
pip freeze --local | grep -v '^\-e' | cut -d = -f 1 | xargs -n1 pip install -U
```

If pip is not on path, use python :
```
python -m pip <command>
```

# Intro
todo


# Command list
Output of pip help :
 - install    : Install packages.
 - download   : Download packages.
 - uninstall  : Uninstall packages.
 - freeze     : Output installed packages in requirements format.
 - list       : List installed packages.
 - show       : Show information about installed packages.
 - check      : Verify installed packages have compatible dependencies.
 - config     : Manage local and global configuration.
 - search     : Search PyPI for packages.
 - wheel      : Build wheels from your requirements.
 - hash       : Compute hashes of package archives.
 - completion : A helper command used for command completion.
 - help       : Show help for commands.

# Commands
## help
Pour voir la listes des commandes disponibles :
To see all
```
pip help
```

### help <command>
To get help on a specific command
```
pip help install
```

## search <package>
To search for a specific package
```
pip search numpy
```

## install <package>
To install a package
```
pip install numpy
```

### install <package>==1.0
To install a specific version of a package

### install '<package>>=1.0'
To install a package with a minimum version

### install -r <requirement file>
Install all packages of a requirement file (-r for requirement)
```
pip install -r requirements.txt
```

### install --upgrade -U <package>
Updage a specific package
```
pip install -U setuptools
```

## list
List all the installed packages
```
pip list
```

### list --outdated -o
List all outdated packages
```
pip list --outdated # -o
```

## uninstall <package>
Uninstall a package
```
pip uninstall Pympler
```

## show <package>
Show infos on a package
```
pip show numpy
```

### show -f --files <package>
List the files installed for a package
```
pip show numpy -f
```

### show -v --verbose <package>
To get more infos on a package

## freeze
List all installed package, and format the list for further use
```
pip freeze
```

### freeze > requirements.txt
Create a requirement file from all installed package
```
pip freeze > requirements.txt
```

# Custom commands
## update all oudated packages
Although not a pip command, you can update all installed packages with a oneliner
```
pip freeze --local | grep -v '^\-e' | cut -d = -f 1 | xargs -n1 pip install -U
```
[source](https://stackoverflow.com/a/3452888/4530214)

## check if a new version is avalaible
```
pip list --outdated | grep numpy
```

## removing all packages
```
pip freeze | xargs pip uninstall -y
```
