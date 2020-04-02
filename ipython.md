

# Quickstart 
 - [Installation](https://ipython.readthedocs.io/en/stable/install/index.html)
 - [Tutorial](https://ipython.readthedocs.io/en/stable/interactive/index.html)
 - [Magic functions](https://ipython.readthedocs.io/en/stable/interactive/magics.html)
 - [IPython Cookbook](https://github.com/ipython/ipython/wiki?path=Cookbook)

Launch IPython : in your terminal : 
```ipython```
To force newline : ENTER or CTRL+o
To force execution : ESC then ENTER

Line magic
```
%run path_to_script.py : run the script in the cell
%load path_to_script.py : insert the script content in the cell
%store variable : save the variable, which can be recovered in another notebook with %store -r variable
%who : list current namespace variables
%who str : list string variables
%whos : table of current namespace
%cd : change working directory
%bookmark here : bookmard current wd as 'here'
%timeit : times the following code (see %%timeit for cell)
%automagic : can be set to True/False, let's you call line magic functions without the % 
%run -d theprogram.py : run script in debugging mode
%run file.py : run file that can be written with %%writefile
%pdoc <object> : prints the object's docstring
%pdef <object> : prints the object signature
%psource <object> : prints the object's source code
%pfile <object> : prints the objects's file source code
%hist -g somestring : search through command history
%env : get variable environement list
%notebook filename : export the session history to a notebook
%psearch a*            -> objects beginning with an a
%psearch -e builtin a* -> objects NOT in the builtin space starting in a
%psearch a* function   -> all functions beginning with an a
%psearch re.e*         -> objects beginning with an e in module re
%psearch r*.e*         -> objects that start with e in modules starting in r
%psearch r*.* string   -> all strings in modules beginning with r
```

Cell magic 
```
%%timeit : times the cell code (see %timeit for line)
%%writefile new_script.py : save cell content in new_script.py
%%HTML : render cell as HTML
%%latex
%%markdown
%%script python2 : will run the content of the cell like a script to python 2
```
Others
```
np.array? : display object docstring
np.array?? : display object source code
TAB : use TAB for auto-completion (see also [jedi](https://ipython.readthedocs.io/en/stable/interactive/tutorial.html#tab-completion))
!ls : execute ls command in shell
var = !cmd : catch shell output and store result in a python variable
```

# Displaying capabilities


Latex : use the %%latex magic cell function or 
```
from IPython.display import Latex
Latex(r"""\begin{eqnarray}
\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} & = \frac{4\pi}{c}\vec{\mathbf{j}} \\
\nabla \cdot \vec{\mathbf{E}} & = 4 \pi \rho \\
\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} & = \vec{\mathbf{0}} \\
\nabla \cdot \vec{\mathbf{B}} & = 0 
\end{eqnarray}""")
```

# Help and debug
```
%lsmagic : list all magic functions
%quickref : quick references of IPython
%magic : info on magic functions
? : help with IPython
```

# Mac screens
```
%config InlineBackend.figure_format = 'retina' # Meilleur plot sur les écrans rétina
```

# Magic functions
There are 2 types of magic functions: 
 - line magic functions, called with %name
 - cell magic function, called with %%name

# Extensions
[Extensions index](https://github.com/ipython/ipython/wiki/Extensions-Index)
Install and use ipython extensions : 
```
pip install birdseye
```
```
%load_ext birdseye
```
Extensions can be placed as scripts in the IPython direction, probably `~/.ipython/`
Then use in a code cell `%%eye`
Also, extensions can be placed in `.ipython/extensions/`
To load an extension at each start : in the configuration file
```
c.InteractiveShellApp.extensions = [
    'myextension'
]
```
## Install extension from script
Get the IPython directory with `ipython locate`, probably in `~/.ipython/profile_default/`. 
Note that the settings in `ipython_config.py` apply to all IPython commands.
Place the extension's script in the `~/.ipython/extensions/` folder, load with `%load_ext pep8_magic ` and call with `%%pep8 `
To load an extension at each start : in the configuration file
```
c.InteractiveShellApp.extensions = [
    'pep8_magic'
]
```

Usefull extensions : 
 - [py2tex](https://github.com/BekeJ/py2tex)
 - [physics](https://github.com/birkenfeld/ipython-physics)
 - [pep8](https://github.com/SiggyF/notebooks)
 - [Matlab](https://github.com/arokem/python-matlab-bridge)
 
# Python path
[see](https://ipython.readthedocs.io/en/stable/interactive/reference.html#ipython-as-your-default-python-environment)
To launch IPython at Python startup, 
place the following code in the PYTHONSTARTUP file 
```
import os, IPython
os.environ['PYTHONSTARTUP'] = ''  # Prevent running this again
IPython.start_ipython()
raise SystemExit
```
The python startup file can be typicaly ~/.pythonstartup

Then add in the .bash_profile file
```
export PYTHONPATH="/Users/mocquin/MYLIB10/MODULES/"
export PYTHONSTARTUP="/Users/mocquin/.pythonstartup"
```


# Tutorial
[here](https://nbviewer.jupyter.org/github/ipython/ipython/blob/master/examples/IPython%20Kernel/Index.ipynb)

# Display
how to implement/use the display functions : [here](https://nbviewer.jupyter.org/github/ipython/ipython/blob/master/examples/IPython%20Kernel/Custom%20Display%20Logic.ipynb)

## Latex
3 possible ways:
```
from IPython.display import Math
Math(r'F(k) = \int_{-\infty}^{\infty} f(x) e^{2\pi i k} dx')
```
```
from IPython.display import Latex
Latex(r"""\begin{eqnarray}
\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} & = \frac{4\pi}{c}\vec{\mathbf{j}} \\
\nabla \cdot \vec{\mathbf{E}} & = 4 \pi \rho \\
\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} & = \vec{\mathbf{0}} \\
\nabla \cdot \vec{\mathbf{B}} & = 0 
\end{eqnarray}""")
```
```
%%latex
\begin{align}
\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} & = \frac{4\pi}{c}\vec{\mathbf{j}} \\
\nabla \cdot \vec{\mathbf{E}} & = 4 \pi \rho \\
\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} & = \vec{\mathbf{0}} \\
\nabla \cdot \vec{\mathbf{B}} & = 0
\end{align}
```


# Config file
Example :
```
c.InteractiveShellApp.exec_lines = [
    'import numpy',
    'import scipy'
]
c.InteractiveShellApp.exec_files = [
    'mycode.py',
    'fancy.ipy'
]
```

# Ressources
## Doc 
https://ipython.readthedocs.io/en/stable/
## Others
https://blog.dominodatalab.com/interactive-dashboards-in-jupyter/  
http://ipywidgets.readthedocs.io/en/latest/examples/Using%20Interact.html  
https://jupyter.org/documentation.html  
http://eric-pommereau.developpez.com/tutoriels/introduction-ipython/