
# Quickstart
```
pip install virtualenv
pip install --user virtualenv
python -m venv
python3 -m venv jupyter_blog_venv
virtualenv my_venv
source my_venv/bin/activate
deactivate
rm -rf my_venv
virtualenv -p /usr/bin/python2.6 my_venv_py26
```

Convention : place venv in project folder, and add venv to .gitignore.

# Debug
```
venv -h
python -m venv
```

# Others
To inherit or not from OS venv : --no-site-packages ou --system-site-packages

