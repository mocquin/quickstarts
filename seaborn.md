
# Quickstart
```python
import seaborn as sns

sns.set_theme() #palette="magma"
iris = sns.load_dataset("iris")


```

# Seaborn plots and objects

Figure level plots : create their own figure, accept `col` to create facet, `kind`, return a `FacetGrid` instance : 

- `displot` : defaults to scatterplot with `FacetGrid
- `relplot` : defaults to histplot with `FacetGrid
- `catplot` : defaults to stripplot with `FacetGrid
- `jointplot` : return a JointGrid
- `pairplot` : return a PairGrid
- `lmplot` : combine `regplot` and `FacetGrid`

Axes-level plots : act like drop-in replacements for matplotlib function, call matplotlib.pyplot.gca() internally, additionally accept an ax= argument

 - `barplot()` : `catplot(kind="bar")`
 - `boxplot()` : `catplot(kind="box)`
 - `boxenplot()` : `catplot(kind="boxen")`
 - `countplot()` : `catplot(kind="count")`
 - `kdeplot()` : `displot(kind="kde")`
 - `ecdfplot()` : `displot(kind="ecdf")`
 - `heatmap()`
 - `histplot()`
 - `sns.lineplot()`
 - `regplot()`
 - `residplot()`
 - `scatterplot()`
 - `stripplot` : `catplot(kind="strip")`
 - `swarmplot` : `catplot(kind="swarm")`
 - `violinplot()` : `catplot(kind="violin")`
 - `pointplot()` : `catplot(kind="point")`
 

Objects : 
 - `FacetGrid`
 - `PairGrid`



# Datasets

```python
# get available datasets
sns.get_dataset_names()
# load dataset
iris_df = sns.load_dataset("iris")
```
List of datasets : 
 - anagrams 
 - anscombe 
 - attention 
 - brain_networks 
 - car_crashes 
 - diamonds 
 - dots 
 - exercise 
 - flights 
 - fmri 
 - gammas 
 - geyser 
 - iris 
 - mpg 
 - penguins 
 - planets 
 - tips 
 - titanic


# Theme, style and context

Seaborn splits matplotlib parameters into two independent groups. The first group sets the aesthetic style of the plot, and the second scales various elements of the figure so that it can be easily incorporated into different contexts.  
The interface for manipulating these parameters are two pairs of functions. To control the style, use the axes_style() and set_style() functions. To scale the plot, use the plotting_context() and set_context() functions. In both cases, the first function returns a dictionary of parameters and the second sets the matplotlib defaults.

```python
sns.set_theme()        # set style and context

sns.axes_style()       # control style, returns a dictionnary of params
sns.plotting_context() # control context, returns a dictionnary of params

sns.set_style()        # sets matplotlib default
sns.set_context()      # sets matplotlib default
```

## Theme


To activate default theme of seaborn : 
```python
sns.set_theme()
seaborn.set_theme(
    context='notebook',
    style='darkgrid',
    palette='deep',
    font='sans-serif',
    font_scale=1, 
    color_codes=True,
    rc=None
)
#seaborn.set(*args, **kwargs) : Alias for set_theme(), which is preferred
sns.set(rc={'figure.figsize': (12, 10)})
```

## Style


To activate style : 
```python
sns.set_style("darkgrid")
sns.set_style("whitegrid")
sns.set_style("dark")
sns.set_style("white")
sns.set_style("ticks")

sns.set_style("darkgrid", {'axes.axisbelow': False})
sns.set_style("darkgrid")

print(sns.axes_style())

{'axes.facecolor': 'white',
 'axes.edgecolor': 'black',
 'axes.grid': False, 
 'axes.axisbelow': 'line',
 'axes.labelcolor': 'black',
 'figure.facecolor': (1, 1, 1, 0), 
 'grid.color': '#b0b0b0',
 'grid.linestyle': '-', 
 'text.color': 'black',
 'xtick.color': 'black', 
 'ytick.color': 'black',
 'xtick.direction': 'out',
 'ytick.direction': 'out',
 'lines.solid_capstyle': 'projecting',
 'patch.edgecolor': 'black',
 'patch.force_edgecolor': False, 
 'image.cmap': 'viridis', 
 'font.family': ['sans-serif'], 
 'font.sans-serif': ['DejaVu Sans', 'Bitstream Vera Sans', 'Computer Modern Sans Serif', 'Lucida Grande',                          'Verdana', 'Geneva', 'Lucid', 'Arial', 'Helvetica', 'Avant Garde', 'sans-serif'], 
 'xtick.bottom': True,
 'xtick.top': False, 
 'ytick.left': True,
 'ytick.right': False,
 'axes.spines.left': True, 
 'axes.spines.bottom': True,
 'axes.spines.right': True, 
 'axes.spines.top': True
}
```
Style can be used in context :
```python
with sns.axes_style("whitegrid"):
    ax = f.add_subplot(gs[1, 1])
    sinplot()
```

```python
import seaborn as sns
import numpy as np
import matplotlib.pyplot as plt
x, y = np.arange(20).reshape(2, 10)

# matplotlib
f, ax = plt.subplots()
ax.plot(x, y)
ax.set_title("matplotlib")

# seaborn
with sns.axes_style("darkgrid"):
    f, ax = plt.subplots()
    ax.plot(x, y)
    ax.set_title("darkgrid")
with sns.axes_style("whitegrid"):
    f, ax = plt.subplots()
    ax.plot(x, y)
    ax.set_title("whitegrid")
with sns.axes_style("dark"):
    f, ax = plt.subplots()
    ax.plot(x, y)
    ax.set_title("dark")
with sns.axes_style("white"):
    f, ax = plt.subplots()
    ax.plot(x, y)
    ax.set_title("white")
with sns.axes_style("ticks"):
    f, ax = plt.subplots()
    ax.plot(x, y)
    ax.set_title("ticks")
```


## Context

Context sizes : paper < notebook < talk < poster
(notebook parameters scaled by .8, 1.3, and 1.6, respectively)
Determined by the dict : 

{'font.size': 10.0,
 'axes.labelsize': 'medium',
 'axes.titlesize': 'large',
 'xtick.labelsize': 'medium',
 'ytick.labelsize': 'medium',
 'legend.fontsize': 'medium',
 'axes.linewidth': 0.8,
 'grid.linewidth': 0.8,
 'lines.linewidth': 1.5,
 'lines.markersize': 6.0,
 'patch.linewidth': 1.0,
 'xtick.major.width': 0.8,
 'ytick.major.width': 0.8,
 'xtick.minor.width': 0.6,
 'ytick.minor.width': 0.6,
 'xtick.major.size': 3.5,
 'ytick.major.size': 3.5,
 'xtick.minor.size': 2.0,
 'ytick.minor.size': 2.0,
 'legend.title_fontsize': None}

```python
# dict of params
sns.plotting_context()

sns.set_context("paper")
sns.set_context("notebook")
sns.set_context("talk")
sns.set_context("poster")

with sns.plotting_context("paper"):
    # do things

    
import seaborn as sns
import matplotlib.pyplot as plt
import numpy as np
x, y = np.arange(20).reshape(2, 10)

# matplotlib
f, ax = plt.subplots()
ax.plot(x, y)
ax.set_title("matplotlib")
# seaborn plotting context
with sns.plotting_context("paper"):
    f, ax = plt.subplots()
    ax.plot(x, y)
    ax.set_title("paper")
with sns.plotting_context("notebook"):
    f, ax = plt.subplots()
    ax.plot(x, y)
    ax.set_title("notebook")
with sns.plotting_context("talk"):
    f, ax = plt.subplots()
    ax.plot(x, y)
    ax.set_title("talk")
with sns.plotting_context("poster"):
    f, ax = plt.subplots()
    ax.plot(x, y)
    ax.set_title("poster")
```


# Palettes

Seaborn palettes : 
 - deep
 - muted
 - bright
 - pastel
 - dark
 - colorblind
 
 Accepted palettes : 

 - Name of a seaborn palette (deep, muted, bright, pastel, dark, colorblind)
 - Name of matplotlib colormap
 - ‘husl’ or ‘hsl’
 - ‘ch:cubehelix arguments’
 - ‘light:color’, ‘dark:color’, ‘blend:color,color’,
 - A sequence of colors in any format matplotlib accepts

 
Seaborn set_palette : 
```python
seaborn.set_palette(
    palette,
    n_colors=None,
    desat=None, 
    color_codes=False
)
```

Seaborn color_palette : 
```python
sns.color_palette(
    palette=None,  # Name of palette or None to return current palette
    n_colors=None, # Number of colors in the palette. If None, the default will depend on how palette is specified. Named palettes default to 6 colors
    desat=None,    # Proportion to desaturate each color by.
    as_cmap=False  # If True, return a matplotlib.colors.Colormap.
)
```
Calling this function with palette=None will return the current matplotlib color cycle.
This function can also be used in a with statement to temporarily set the color cycle for a plot or set of plots.


To plot a palette : 
```python
sns.palplot(sns.color_palette("magma"))
``` 

```python
palette_list = ['Accent', 'Accent_r', 'Blues', 'Blues_r', 'BrBG', 'BrBG_r', 'BuGn', 'BuGn_r', 'BuPu', 'BuPu_r',
         'CMRmap', 'CMRmap_r', 'Dark2', 'Dark2_r', 'GnBu', 'GnBu_r', 'Greens', 'Greens_r', 'Greys',
         'Greys_r', 'OrRd', 'OrRd_r', 'Oranges', 'Oranges_r', 'PRGn', 'PRGn_r', 'Paired', 'Paired_r',
         'Pastel1', 'Pastel1_r', 'Pastel2', 'Pastel2_r', 'PiYG', 'PiYG_r', 'PuBu', 'PuBuGn', 'PuBuGn_r',
         'PuBu_r', 'PuOr', 'PuOr_r', 'PuRd', 'PuRd_r', 'Purples', 'Purples_r', 'RdBu', 'RdBu_r', 'RdGy',
         'RdGy_r', 'RdPu', 'RdPu_r', 'RdYlBu', 'RdYlBu_r', 'RdYlGn', 'RdYlGn_r', 'Reds', 'Reds_r',
         'Set1', 'Set1_r', 'Set2', 'Set2_r', 'Set3', 'Set3_r', 'Spectral', 'Spectral_r', 'Wistia',
         'Wistia_r', 'YlGn', 'YlGnBu', 'YlGnBu_r', 'YlGn_r', 'YlOrBr', 'YlOrBr_r', 'YlOrRd',
         'YlOrRd_r', 'afmhot', 'afmhot_r', 'autumn', 'autumn_r', 'binary', 'binary_r', 'bone', 'bone_r',
         'brg', 'brg_r', 'bwr', 'bwr_r', 'cividis', 'cividis_r', 'cool', 'cool_r', 'coolwarm', 'coolwarm_r',
         'copper', 'copper_r', 'cubehelix', 'cubehelix_r', 'flag', 'flag_r', 'gist_earth', 'gist_earth_r',
         'gist_gray', 'gist_gray_r', 'gist_heat', 'gist_heat_r', 'gist_ncar', 'gist_ncar_r', 'gist_rainbow',
         'gist_rainbow_r', 'gist_stern', 'gist_stern_r', 'gist_yarg', 'gist_yarg_r', 'gnuplot', 'gnuplot2',
         'gnuplot2_r', 'gnuplot_r', 'gray', 'gray_r', 'hot', 'hot_r', 'hsv', 'hsv_r', 'icefire',
         'icefire_r', 'inferno', 'inferno_r', 'jet_r', 'magma', 'magma_r', 'mako', 'mako_r', 'nipy_spectral',
         'nipy_spectral_r', 'ocean', 'ocean_r', 'pink', 'pink_r', 'plasma', 'plasma_r', 'prism',
         'prism_r', 'rainbow', 'rainbow_r', 'rocket', 'rocket_r', 'seismic', 'seismic_r', 'spring',
         'spring_r', 'summer', 'summer_r', 'tab10', 'tab10_r', 'tab20', 'tab20_r', 'tab20b', 'tab20b_r',
         'tab20c', 'tab20c_r', 'terrain', 'terrain_r', 'turbo', 'turbo_r', 'twilight', 'twilight_r',
         'twilight_shifted', 'twilight_shifted_r', 'viridis', 'viridis_r', 'vlag', 'vlag_r', 'winter',
         'winter_r']
```
`_r` means reverse


# Despine
```python
sns.despine(
    fig=None,
    ax=None, 
    top=True,
    right=True,
    left=False,
    bottom=False,
    offset=None,  # distance between spines
    trim=False
)

sns.despine(fig=fig, left=True, bottom=False, trim=False, offset=10)
```

# Ressources

 - https://www.kaggle.com/themlphdstudent/cheat-sheet-seaborn-charts
 - https://seaborn.pydata.org/introduction.html
 - https://seaborn.pydata.org/tutorial.html
 - https://jakevdp.github.io/PythonDataScienceHandbook/04.14-visualization-with-seaborn.html
 - https://medium.com/@neuralnets/statistical-data-visualization-series-with-python-and-seaborn-for-data-science-5a73b128851d
 - https://medium.com/@ppeng08/interactive-visualization-for-exploratory-data-analysis-in-jupyter-notebook-adc826e1e76a
 - https://gist.github.com/noklam/ddd503085c5aa0c27ddb0eceb4a2f07b
 - https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Python_Seaborn_Cheat_Sheet.pdf
 - https://python.quantecon.org/index_toc.html
 - http://seaborn.pydata.org/tutorial/axis_grids.html
 - http://seaborn.pydata.org/tutorial/axis_grids.html#conditional-small-multiples
 - https://www.youtube.com/watch?v=KvZ2KSxlWBY 
 - https://github.com/micgonzalez/Data-Visualization-of-Pokemon-Data-with-Python-and-Seaborn_side_project
 - https://github.com/pseudoPixels/iSeaborn
 - https://github.com/chmduquesne/quickviz
 - https://www.tutorialspoint.com/seaborn/index.htm



# Plots interfaces 
