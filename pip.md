# Quickstart
```
pip help
pip install numpy==1.0
pip install numpy>=1.0
pip show numpy
pip show -f numpy
pip show -v numpy
pip search numpy
pip install --upgrade numpy
pip install --upgrade numpy --verbose
pip uninstall numpy
pip list
pip list --outdated
pip freeze
pip freeze > reqs.txt
pip install -r requirements.txt
pip --version
```

# Debug
If pip is not on path, use python :
```
python -m pip <command>
```
To check if/where pip is installed :
```
which pip
pip -V
```

# Custom commands
Update all oudated packages
```
pip freeze --local | grep -v '^\-e' | cut -d = -f 1 | xargs -n1 pip install -U
```
[source](https://stackoverflow.com/a/3452888/4530214)

Check if new version is avalaible
```
pip list --outdated | grep numpy
```

Removing all packages
```
pip freeze | xargs pip uninstall -y
```
