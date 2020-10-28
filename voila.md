# voila

Command line software and jupyterlab extension to turn a notebook into a web page linked to python kernel, allowing python-callback interactions (instead of just static HTML-exported notebook).
It differs from nbconvert in that the output web application is connected to a Jupyter kernel, allowing it to respond to user input through widget controls and other UI components, while with nbconvert, any action that requires a roundtrip to the kernel will not work.


## CLI usage
This will open a web page with the result interactive dashboard:
`voila my_notebook_with_widgets.ipynb`

By default, Voilà runs at localhost:8866. Running `voila`in a directory will open a file browser that can render notebooks.

Common args : 
 - `--strip_sources=False` : By default, the code cells are stripped. To keep the code-cells, strip_sources is set to False
 - `--theme=dark`: change theme

## voila jupyterlab extension
`jupyter labextension install @jupyter-voila/jupyterlab-preview`

2 possibilities : 
 - display the rendered voila in a side-pane : View -> Render Notebook with Voila
 - display the rendered voila in a new browser tab : View -> Open Voila in new Browser tab

Also, in notebook toolbar, click on Voila icon to render in new side-pane

 
# Custom templates
 - https://github.com/voila-dashboards/voila-gridstack
 - https://github.com/voila-dashboards/voila-material
 - https://github.com/voila-dashboards/voila-vuetify
 
# ressources
 - https://github.com/voila-dashboards/voila
 - https://voila-gallery.org/
 - https://voila.readthedocs.io/en/stable/index.html
 - https://github.com/voila-dashboards/voila
 - https://github.com/voila-dashboards/voila/tree/master/notebooks
 - https://blog.jupyter.org/and-voil%C3%A0-f6a2c08a4a93
 