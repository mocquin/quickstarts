# Version, backend

```python
matplotlib.__version__
matplotlib.get_backend() : returns rcParams['backend']
matplotlib.use('nbagg') : use backend
plt.ion()/off() : activate/deactivate immediately display objects 
%matplotlib backend_name : set backend to nbagg, and plt.ion()
```

 - `matplotlib.rcsetup.interactive_bk` : list interactive backends
 - `matplotlib.rcsetup.non_interactive_bk` : list non interactiv backends
 - `matplotlib.rcsetup.all_backends` : list all backends
 
# rcParams, style sheet

`matplotlib.matplotlib_fname() : rc file path`  
`mpl.rcdefaults() : reset rc file to default`  
`mpl.rc('lines', linewidth=2, linestyle='-.') : dynamic change of rc file`  
`#mpl.rcParams['lines.linewidth'] = 2`  
`#mpl.rcParams['lines.linestyle'] = '-.'`  
`plt.rcParams['text.usetex'] = True`: use latex


`plt.style.use('ggplot')` : use ggplot style
`plt.style.use('url to style sheet')` : use style sheet at url
`matplotlib.get_configdir()` : config dir
`style.use(style-name)`: use the style-name.mplstyle file of the folder mpl_configdir/stylelib
`plt.style.available` : list available styles

 
# axes creation

 - method 1 : 
```python
fig = plt.figure()
ax = fig.add_subplot(1,1,1) # make a blank plotting area'
```


 - method 2 : 
```python
fig, ax = plt.subplots()
```


 - method 3 :
```python
fig, axes = plt.subplots(nrows=2, ncols=2) : where axes is a numpy array of Axes objects
```


# plot and lines

```python
line1, = ax.plot(x, np.sin(x), label='1st plot') 
print(ax.lines)
```


# main attributes 

 - `fig.axes`: list of axes
 - `ax.figure`: parent figure of ax
 - `ax.xaxis`: XAxis of ax
 - `ax.xaxis.axes`: ax
 - `ax.xaxis.figure`: ax's figure
 - `ax.lines`: list of Line2D objects


## Figure attributes

 - `fig.axes` 	: A list of Axes instances (includes Subplot)
 - `fig.patch` 	: The Rectangle background
 - `fig.images` 	: A list of FigureImages patches - useful for raw pixel display
 - `fig.legends` 	: A list of Figure Legend instances (different from Axes.legends)
 - `fig.lines` 	: A list of Figure Line2D instances (rarely used, see Axes.lines)
 - `fig.patches` 	: A list of Figure patches (rarely used, see Axes.patches)
 - `fig.texts` 	: A list Figure Text instances


## Axes attributes 	
 - `ax.artists` 	  : A list of Artist instances
 - `ax.patch` 	  : Rectangle instance for Axes background
 - `ax.collections` : A list of Collection instances
 - `ax.images` 	  : A list of AxesImage
 - `ax.legends` 	  : A list of Legend instances
 - `ax.lines` 	  : A list of Line2D instances
 - `ax.patches` 	  : A list of Patch instances
 - `ax.texts` 	  : A list of Text instances
 - `ax.xaxis` 	  : matplotlib.axis.XAxis instance
 - `ax.yaxis` 	  : matplotlib.axis.YAxis instance

Axes helper functions : 
 - `ax.annotate` 	: adds object Annotate 	         to ax.texts
 - `ax.bar` 	    : adds object Rectangle 	     to ax.patches
 - `ax.errorbar` 	: adds object Line2D & Rectangle to ax.lines & ax.patches
 - `ax.fill` 	    : adds object Polygon 	         to ax.patches
 - `ax.hist` 	    : adds object Rectangle 	     to ax.patches
 - `ax.imshow` 	: adds object AxesImage 	     to ax.images
 - `ax.legend` 	: adds object Legend 	         to ax.legends
 - `ax.plot`   	: adds object Line2D 	         to ax.lines
 - `ax.scatter` 	: adds object PathCollection 	 to ax.collections
 - `ax.text` 	    : adds object Text 	             to ax.texts

## Axis attributes
 - `axis.label` 	   : A Text instance for axis label
 - `axis.majorTicks` : A list of Tick instances for major ticks.
 - `axis.minorTicks` : A list of Tick instances for minor ticks

# containers artists

 - Figure
 - Axes
 - Axis
 - Tick
 
see [this](https://res.cloudinary.com/practicaldev/image/fetch/s--KMJNInQX--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/la33f9zwg65hqjz9j4ee.png)


# Imshow
`matplotlib.pyplot.imshow(X, cmap=”gray”, norm=None, aspect=None, interpolation=None, alpha=None, vmin=None, vmax=None)`

# Artists patches 
```python
# rectangle
axes.add_artist(
    patches.Rectangle((0.2, 0.2), 0.4, 0.3,
                      edgecolor = 'black', facecolor = 'orange',
                      fill = True, hatch = '/', linestyle = 'dashed',
                      linewidth = 3, zorder = 1))
# Circle
axes.add_artist(
    patches.Circle((0.5, 0.6), 0.15, color = 'cyan', zorder = 2))
# Ellipse
axes.add_artist(
    patches.Ellipse((0.2, 0.7), 0.3, 0.2, 45,
                    edgecolor = 'magenta', facecolor = 'yellow', zorder = 2))
# Arc
axes.add_artist(
    patches.Arc((0.7, 0.7), 0.3, 0.2, 20, 0, 120, color = 'red', linewidth = 5))
```
 
figure():
-          figsize=plt.figaspect(2.0)
-          facecolor=(1, 0, 0, .1)
 
`ax.axhline(0, color='gray', linewidth=2)`   
`ax.set_xlim([0.5, 4.5])`   
`ax.set_ylim([-2, 8])`   
`ax.set_title('A Different Example Axes Title')`   
`ax.set_ylabel('Y-Axis (changed)')`   
`ax.set_xlabel('X-Axis (changed)')`   
equivalent to
`ax.set(xlim=[0.5, 4.5], ylim=[-2, 8], title='An Example Axes',
       ylabel='Y-Axis', xlabel='X-Axis')`
 
 
plt.show()
 
# data argument

```python
x = np.linspace(0, 10, 200)
data_obj = {'x': x,
            'y1': 2 * x + 1,
            'y2': 3 * x + 1.2,
            'mean': 0.5 * x * np.cos(2*x) + 2.5 * x + 1.1}
fig, ax = plt.subplots()
# Plot the envelope with `fill_between`
ax.fill_between('x', 'y1', 'y2', color='yellow', data=data_obj)
# Plot the "centerline" with `plot`
ax.plot('x', 'mean', color='black', data=data_obj)
```
 
#O verlapping colorbar
```python
cax = fig.add_axes([0.27, 0.8, 0.5, 0.05])
im = ax.imshow(data, cmap='gist_earth')
fig.colorbar(im, cax=cax, orientation='horizontal')
```

 
 
# axis
```python
xmin, xmax, ymin, ymax = ax.axis()
 
ax.axis([xmin, xmax, ymin, ymax])
ax.axis('tight')
ax.axis(‘equal’)
ax1.set_ylim(bottom=-10)
ax2.set_xlim(right=25)
 
ax.set_aspect('equal')
 
#legend
ax.set(ylabel='Temperature (deg C)', xlabel='Time', title='A tale of two cities')
ax.legend()
ax.legend(loc='best')
 
# layout
fig.subplots_adjust(wspace=0.5, hspace=0.3,
                    left=0.125, right=0.9,
                    top=0.9,    bottom=0.1)
fig.tight_layout()
 
# spines
ax.spines['top'].set_visible(False)
 ```
 
ipympl built on top of ipywidgets, and set with %matplotlib widget
ax.get_figure()




line = Line2D(x, y)
ax.add_line(line)




# figure creation
```python
fig = plt.figure()
ax = fig.add_subplot()
```

equivalent method :
```python 
ax = fig.add_subplot(111)# Another equivalent but more general method
ax = fig.add_subplot(1, 1, 1)
```

# Create a figure
fig = plt.figure()
# Create a subplot
ax = fig.subplots()# Equivalent method
ax = fig.subplots(1, 1)


# Create a figure
fig = plt.figure()# Add a subplot 
ax = fig.add_axes([0, 0, 0.78, 0.78])



# Creates just a figure and only one subplot
ax = plt.subplot()# Equivalent method
fig = plt.figure()
ax = fig.add_subplot(1, 1, 1)

# Creates just a figure and only one subplot
```python
fig, ax = plt.subplots()# Equivalent method
fig = plt.figure()
ax = fig.subplots(1, 1)
```

```python
fig = plt.figure()
ax1 = fig.add_subplot(221)
ax2 = fig.add_subplot(222)
ax3 = fig.add_subplot(223)
ax4 = fig.add_subplot(224)
```

```python
fig = plt.figure()
axs = fig.subplots(nrows=2, ncols=2)
```

```python
fig = plt.figure()
((ax1, ax2), (ax3, ax4)) = fig.subplots(nrows=2, ncols=2)
```

```python
fig = plt.figure()
ax1 = fig.add_axes([0, 0.6, 0.5, 0.5])
ax2 = fig.add_axes([0.6, 0.6, 0.5, 0.5])
ax3 = fig.add_axes([0, 0, 0.5, 0.5])
ax4 = fig.add_axes([0.6, 0, 0.5, 0.5])
```

```python
fig, (ax0, ax1) = plt.subplots(ncols=2, constrained_layout=True)
``` 

# Text and annotation
`ax.vlines(x, ymin, ymax)`
`ax.annotate(text, (x, y))`
```python
plt.text(
    0.5, 0.5,
    "This will be in the middle of the ax",
    transform=ax.transAxes,
    horizontalalgment="center",
    )
```
 
Title to figure
fig.suptitle('This is a somewhat long figure title', fontsize=16)

# Styles and customizing
 - Theme examples : http://www.futurile.net/2016/02/27/matplotlib-beautiful-plots-with-style/
 - Theme examples : https://tonysyu.github.io/raw_content/matplotlib-style-gallery/gallery.html
 - Customizing and style : https://matplotlib.org/tutorials/introductory/customizing.html

# Interactive plotting with matplotlib
 - interactive matplotlib intro : https://matplotlib.org/3.3.0/users/interactive.html
 - intro : https://towardsdatascience.com/how-to-produce-interactive-matplotlib-plots-in-jupyter-environment-1e4329d71651
 - navigation toolbar options : https://matplotlib.org/3.2.1/users/navigation_toolbar.html
 - example of interactive app : dragging objects, drawing lines, click/release : https://matplotlib.org/3.2.1/users/event_handling.html
 - example using matplotlib's slider widget : https://riptutorial.com/matplotlib/example/23577/interactive-controls-with-matplotlib-widgets
 - matplotlib's widget examples : https://matplotlib.org/gallery/index.html#widgets
 - ipython matplotlib interactive plotting : https://ipython.readthedocs.io/en/stable/interactive/plotting.html
 - ipython matplotlib magic line : https://ipython.readthedocs.io/en/stable/interactive/magics.html?highlight=magic%20#magic-matplotlib
 - example cursor/hover using matplotlib's widgets : https://www.youtube.com/watch?v=YobjoBrND4w
 - great tricks and examples customizing matplotlib's figure's windows : https://github.com/matplotlib/ipympl/blob/master/examples/ipympl.ipynb
 - tutorial : https://namingcrisis.net/post/2019/03/11/interactive-matplotlib-ipython/
 
 
In any case, matplotlib's figures/axes/etc can be customized to look "user-friendly" (see https://github.com/matplotlib/ipympl/blob/master/examples/ipympl.ipynb)

 - In ipython, get current backend : `%matplotlib`  
 - In python, get current backend : `import matplotlib as mpl;mpl.get_backend()`
 - In python, to use specific backend : `mpl.use('pdf')`
 - In ipython, list available backends : `%matplotlib --list`
 - In default Python prompt : `import matplotlib.pyplot as plt;plt.ion()`  
 - In jupyterlab, the default backend `inline` is not interactive. To get interactive figures, install the [ipympl](https://github.com/matplotlib/ipympl) backend (based on ipywidget) and enable it with : `%matplotlib widget`
 - In jupyter notebook, use `%matplotlib notebook`
 - To disable automatic updating : `plt.ioff()`  
 - To enable automatic updating : `plt.ion()`  
 - To see current interactivity : `pyplot.isinteractive()`

Matplotlib also offers basic widgets : 


The interactive mode allows : 
 - zooming
 - panning
 - reset view
 - save as
 - key-binding, see `rcParams["keymap"]`: 
   - Home/Reset 	rcParams["keymap.home"] (default: ['h', 'r', 'home'])
   - Back 	rcParams["keymap.back"] (default: ['left', 'c', 'backspace', 'MouseButton.BACK'])
   - Forward 	rcParams["keymap.forward"] (default: ['right', 'v', 'MouseButton.FORWARD'])
   - Pan/Zoom 	rcParams["keymap.pan"] (default: ['p'])
   - Zoom-to-rect 	rcParams["keymap.zoom"] (default: ['o'])
   - Save 	rcParams["keymap.save"] (default: ['s', 'ctrl+s'])
   - Toggle fullscreen 	rcParams["keymap.fullscreen"] (default: ['f', 'ctrl+f'])
   - Toggle major grids 	rcParams["keymap.grid"] (default: ['g'])
   - Toggle minor grids 	rcParams["keymap.grid_minor"] (default: ['G'])
   - Toggle x axis scale (log/linear) 	rcParams["keymap.xscale"] (default: ['k', 'L'])
   - Toggle y axis scale (log/linear) 	rcParams["keymap.yscale"] (default: ['l'])
   - Close Figure 	rcParams["keymap.quit"] (default: ['ctrl+w', 'cmd+w', 'q'])
   - Constrain pan/zoom to x axis 	hold x when panning/zooming with mouse
   - Constrain pan/zoom to y axis 	hold y when panning/zooming with mouse
   - Preserve aspect ratio 	hold CONTROL when panning/zooming with mouse
   

Difference between interactive mode and not-interactive mode : 
 - interactive mode : 
   - newly created figures will be displayed immediately
   - figures will automatically redraw when elements are changed
   - pyplot.show() displays the figures and immediately returns
 - not interactive mode : 
   - newly created figures and changes to figures are not displayed until pyplot.show() is called,  or pyplot.pause() is called, or FigureCanvasBase.flush_events() is called
   - pyplot.show() runs the GUI event loop and does not return until all the plot windows are closed

Advanced interactive plotting : 
 - https://github.com/ianhi/mpl-interactions
 - https://mpl-interactions.readthedocs.io/en/latest/

 
 
## backend
 - Backend doc : https://matplotlib.org/3.3.2/tutorials/introductory/usage.html#backends
 - What is interactive mode : https://matplotlib.org/3.3.2/tutorials/introductory/usage.html#what-is-interactive-mode

There are two types of backends: user interface backends (for use in pygtk, wxpython, tkinter, qt4, or macosx; also referred to as "interactive backends") and hardcopy backends to make image files (PNG, SVG, PDF, PS; also referred to as "non-interactive backends").There are three ways to configure your backend:
 - The rcParams["backend"] (default: 'agg') parameter in your matplotlibrc file : backend : qt5agg
 - The MPLBACKEND environment variable : set MPLBACKEND=qt5agg (on windows)
 - The function matplotlib.use() : matplotlib.use('qt5agg')
 

# Saving figures to file

Pickling (use %matplolib ipympl in jupyterlab) :

```python
import matplotlib.pyplot as plt
import pickle

fig, ax =  plt.subplots()
ax.plot(list(range(1, 100, 10)), 'bo-')

# dumps the figure with pickle
with open('fig1.pkl', 'wb') as fs:
    pickle.dump(ax, fs)
plt.close("all")


# load the saved figure as mpl figure
fig = pickle.load(open('fig1.pkl', 'rb'))
plt.show()

plt.show()
```

 

# Ressources 
 - https://matplotlib.org/gallery/#embedding-matplotlib-in-graphical-user-interfaces 
 - https://github.com/matplotlib/GettingStarted/blob/master/notebooks/06-interactive.ipynb
 - https://github.com/matplotlib/matplotlib/blob/0ea20132e306c4607617b61dca7143ea34d30ad0/lib/matplotlib/units.py
 - https://github.com/matplotlib/matplotlib/blob/e70c9d29a359302ed4046c26a74bf566702e1b6c/lib/matplotlib/tests/test_units.py
 - https://github.com/matplotlib/matplotlib/blob/bfda3a47834283436f20a1c79bd1199e2d774201/examples/units/evans_test.py
 - https://github.com/hgrecco/pint/blob/master/pint/matplotlib.py 
 - https://stackoverflow.com/questions/21271195/can-i-use-matplotlib-units-to-switch-between-the-units-displayed-on-a-graph
 - https://github.com/yt-project/unyt
 - https://dev.to/skotaro/artist-in-matplotlib---something-i-wanted-to-know-before-spending-tremendous-hours-on-googling-how-tos--31oo
  - https://towardsdatascience.com/plt-xxx-or-ax-xxx-that-is-the-question-in-matplotlib-8580acf42f44
 - https://matplotlib.org/3.1.1/gallery/style_sheets/style_sheets_reference.html
 - https://towardsdatascience.com/the-many-ways-to-call-axes-in-matplotlib-2667a7b06e06
 - https://github.com/Perishleaf/data-visualisation-scripts/blob/master/matplotlib_init_fig_ax/matplotlib_init_fig_ax.ipynb
 - https://towardsdatascience.com/5-powerful-tricks-to-visualize-your-data-with-matplotlib-16bc33747e05
 - https://towardsdatascience.com/how-to-do-visualization-using-python-from-scratch-651304b5ee7a
 - https://github.com/rougier/matplotlib-cheatsheet
 - https://github.com/matplotlib/cheatsheets
 - https://github.com/rougier/scientific-visualization-book
 - https://github.com/rougier/matplotlib-tutorial
 