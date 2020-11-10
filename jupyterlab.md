

# alternative IDE to watch
 - deepnote : https://deepnote.com/
 - pycharm : https://towardsdatascience.com/are-you-still-using-jupyterlab-ce1a4339c0a9
 

https://discourse.jupyter.org/t/extension-shows-up-as-both-installed-and-uninstalled-and-doesnt-work/2688/3


# Jupyterlab startup folder
Create a file `jupyter_notebook_config.py` in home with `c.NotebookApp.notebook_dir = r”path_to_startup_file”`
 

# nbconvert
nbconvert is part of the jupyter ecosystem and allows conversion of Notebook into various formats.
 - convert notebook to latex without code cell : `jupyter nbconvert --to latex --no-input Example.ipynb `
 - convert notebook to script : `jupyter nbconvert –to script example.ipynb`
 - convert notebook to html : `jupyter nbconvert –to html example.ipynb`
 

# node
You migth need to upgrade node
`brew install node`
`brew upgrade node`


# Toolbox

# extensions
## usage
```
jupyter labextension install jupyter-matplotlib : for %matplotlib widget
jupyter labextension uninstall my-extension
jupyter labextensino list
jupyter labextension update --all
```

## Debug installation problems
https://github.com/jupyterlab/jupyterlab/issues/8122#issuecomment-617209892

## curated list of extensions
see also [https://github.com/mauhai/awesome-jupyterlab](https://github.com/mauhai/awesome-jupyterlab) and [https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/index.html](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/index.html)

My best : 
 - [DrawIO](https://github.com/QuantStack/jupyterlab-drawio) : create figures
 - [Toc](https://github.com/jupyterlab/jupyterlab-toc) : table of content
 - [ipysheet](https://github.com/QuantStack/ipysheet) : spreadsheet
 - [ipywidgets](https://github.com/jupyter-widgets/ipywidgets) : IPython widgets support
 - [debugger](https://github.com/jupyterlab/debugger) : UI debugger
 - [variable inspector](https://github.com/lckr/jupyterlab-variableInspector) : UI variable inspector
 - [qgrid](https://github.com/quantopian/qgrid)
 - [LSP](https://github.com/krassowski/jupyterlab-lsp)
 - [kite](https://github.com/kiteco/jupyterlab-kite)
 

# Ressources 
 - https://github.com/mauhai/awesome-jupyterlab
 - https://github.com/markusschanta/awesome-jupyter#jupyterlab-extensions
 - https://github.com/quobit/awesome-python-in-education#jupyter
 - https://jupyterlab.readthedocs.io/en/stable/user/extensions.html