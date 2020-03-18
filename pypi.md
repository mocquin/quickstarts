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

https://stackoverflow.com/questions/52700692/a-guide-for-updating-packages-on-pypi
https://stackoverflow.com/questions/51451966/twine-not-found-bash-twine-command-not-found
