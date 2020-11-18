# mpld3

> *a simple API for exporting your matplotlib graphics to HTML code which can be used within the browser, within standard web pages, blogs, or tools such as the IPython notebook.*

`pip install mpld3`


 - `mpld3.show()` : Open figure in a web browser
 - `mpld3.fig_to_html()` : Output html representation of the figure
 - `mpld3.display()` : Display figure in IPython notebook via the HTML display hook
 - `mpld3.save_html()` : Save a matplotlib figure to an html file
 

## Offline plots

### Saving graphs for offline html

Download the mpld3 zip from : https://github.com/mpld3/mpld3/archive/master.zip
Unzip the file.
It contains the mpld3 python pacjage, as well as the js libraries.
Install mpld3 with pip.

Saving interactive offline figures to html :
```python
mpld3_url='/path/to/mpld3-master/mpld3/js/mpld3.v0.5.1.js'
d3_url='/path/to/mpld3-master/mpld3/js/d3.v5.min.js'
with open('graph.html', 'w') as fileobj:
    mpld3.save_html(plt.gcf(), fileobj, d3_url=d3_url, mpld3_url=mpld3_url)
```

```python
mpld3.fig_to_html(fig, d3_url=None, mpld3_url=None, no_extras=False, template_type='general', figid=None, use_http=False, **kwargs)[source]
```

See : 

 - https://mpld3.github.io/modules/API.html#mpld3.save_html
 - https://stackoverflow.com/questions/52616907/write-to-an-html-file-with-python
 - https://mpld3.github.io/modules/API.html#mpld3.fig_to_html
 - https://mpld3.github.io/faq.html


### Offline notebook plots : 
Use "local=True" with mpld3.enable_notebook() and mpld3.display().



## jupyterlab/notebooks

To plot inline graphs but that are still interactives : 
```python
import mpld3
mpld3.display(fig)
```
To use mpld3 by default, after calling `%matplotlib inline`:
```python
mpld3.enable_notebook()
```


# plugins

 - selection box on scatter matrix : https://mpld3.github.io/examples/linked_brush.html#linked-brush 
 - tooltip on scatter plot : https://mpld3.github.io/examples/scatter_tooltip.html#scatter-tooltip
 - html tooltip on scatter plot : https://mpld3.github.io/examples/html_tooltips.html#html-tooltips
 - highlight line on hover : https://mpld3.github.io/examples/random_walk.html#random-walk
 - hide and/or high on hover/click in legend with labels : https://mpld3.github.io/examples/interactive_legend.html
 - update graph on hover : https://mpld3.github.io/examples/custom_plugin.html