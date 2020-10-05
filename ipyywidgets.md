


# Ressources
http://ipywidgets.readthedocs.io/en/latest/index.html
https://github.com/jupyter-widgets/tutorial
https://gitter.im/jupyter-widgets/Lobby
https://github.com/JuanCab/AstroInteractives
https://github.com/jupyter-widgets/ipywidgets/blob/master/docs/source/examples/Index.ipynb



# quickstart 
```python
import ipywidgets as widgets
```


# Widgets list

## Numeric widgets
### Intslider
```python
widgets.IntSlider(
    value=7,
    min=0,
    max=10,
    step=1,
    description='Test:',
    disabled=False,
    continuous_update=False,
    orientation='horizontal',
    readout=True,
    readout_format='d'
)
```

### FloatSlider
```python
widgets.FloatSlider(
    value=7.5,
    min=0,
    max=10.0,
    step=0.1,
    description='Test:',
    disabled=False,
    continuous_update=False,
    orientation='horizontal',
    readout=True,
    readout_format='.1f',
)
```

### FloatLogSlider
```python
widgets.FloatLogSlider(
    value=10,
    base=10,
    min=-10, # max exponent of base
    max=10, # min exponent of base
    step=0.2, # exponent step
    description='Log Slider'
)
```

### IntRangeSlider
```python
widgets.IntRangeSlider(
    value=[5, 7],
    min=0,
    max=10,
    step=1,
    description='Test:',
    disabled=False,
    continuous_update=False,
    orientation='horizontal',
    readout=True,
    readout_format='d',
)
```
### FloatRangeSlider
```python
widgets.FloatRangeSlider(
    value=[5, 7.5],
    min=0,
    max=10.0,
    step=0.1,
    description='Test:',
    disabled=False,
    continuous_update=False,
    orientation='horizontal',
    readout=True,
    readout_format='.1f',
)
```

### IntProgress
```python
widgets.IntProgress(
    value=7,
    min=0,
    max=10,
    step=1,
    description='Loading:',
    bar_style='', # 'success', 'info', 'warning', 'danger' or ''
    orientation='horizontal'
)
```

### FloatProgress
```python
widgets.FloatProgress(
    value=7.5,
    min=0,
    max=10.0,
    step=0.1,
    description='Loading:',
    bar_style='info',
    orientation='horizontal'
)
```

### BoundedIntText
```python
widgets.BoundedIntText(
    value=7,
    min=0,
    max=10,
    step=1,
    description='Text:',
    disabled=False
)
```

### IntText
```python
widgets.IntText(
    value=7,
    description='Any:',
    disabled=False
)
```

### FloatText
```python
widgets.FloatText(
    value=7.5,
    description='Any:',
    disabled=False
)
```

## Boolean widgets
### ToggleButton
```python
widgets.ToggleButton(
    value=False,
    description='Click me',
    disabled=False,
    button_style='', # 'success', 'info', 'warning', 'danger' or ''
    tooltip='Description',
    icon='check' # (FontAwesome names without the `fa-` prefix)
)
```

### Checkbox
```python
widgets.Checkbox(
    value=False,
    description='Check me',
    disabled=False,
    indent=False
)
```

### Valid
```python
widgets.Valid(
    value=False,
    description='Valid!',
)
```

## Selection widget
### Dropdown
```python
widgets.Dropdown(
    options=['1', '2', '3'],
    value='2',
    description='Number:',
    disabled=False,
)
```
```python
widgets.Dropdown(
    options=[('One', 1), ('Two', 2), ('Three', 3)],
    value=2,
    description='Number:',
)
```

### RadioButtons
```python
widgets.RadioButtons(
    options=['pepperoni', 'pineapple', 'anchovies'],
#    value='pineapple', # Defaults to 'pineapple'
#    layout={'width': 'max-content'}, # If the items' names are long
    description='Pizza topping:',
    disabled=False
)
```

### Select
```python
widgets.Select(
    options=['Linux', 'Windows', 'OSX'],
    value='OSX',
    # rows=10,
    description='OS:',
    disabled=False
)
```

### SelectionSlider
```python
widgets.SelectionSlider(
    options=['scrambled', 'sunny side up', 'poached', 'over easy'],
    value='sunny side up',
    description='I like my eggs ...',
    disabled=False,
    continuous_update=False,
    orientation='horizontal',
    readout=True
)
```

### SelectionRangeSlider
```python
import datetime
dates = [datetime.date(2015, i, 1) for i in range(1, 13)]
options = [(i.strftime('%b'), i) for i in dates]
widgets.SelectionRangeSlider(
    options=options,
    index=(0, 11),
    description='Months (2015)',
    disabled=False
)
```



### ToggleButtons
```python
widgets.ToggleButtons(
    options=['Slow', 'Regular', 'Fast'],
    description='Speed:',
    disabled=False,
    button_style='', # 'success', 'info', 'warning', 'danger' or ''
    tooltips=['Description of slow', 'Description of regular', 'Description of fast'],
#     icons=['check'] * 3
)
```

### SelectMultiple
```python
widgets.SelectMultiple(
    options=['Apples', 'Oranges', 'Pears'],
    value=['Oranges'],
    #rows=10,
    description='Fruits',
    disabled=False
)
```

## String widgets

### Text
```python
widgets.Text(
    value='Hello World',
    placeholder='Type something',
    description='String:',
    disabled=False
)
```

### TextArea
```python
widgets.Textarea(
    value='Hello World',
    placeholder='Type something',
    description='String:',
    disabled=False
)
```

### Combobox
```python
widgets.Combobox(
    # value='John',
    placeholder='Choose Someone',
    options=['Paul', 'John', 'George', 'Ringo'],
    description='Combobox:',
    ensure_option=True,
    disabled=False
)
```

### Password
```python
widgets.Password(
    value='password',
    placeholder='Enter password',
    description='Password:',
    disabled=False
)
```

### Label
```python
widgets.HBox([widgets.Label(value=r"The $m$ in $E=mc^2$:"), widgets.FloatSlider()])
```

### HTML
```python
widgets.HTML(
    value="Hello <b>World</b>",
    placeholder='Some HTML',
    description='Some HTML',
)
```

### HTMLMath
```python
widgets.HTMLMath(
    value=r"Some math and <i>HTML</i>: \(x^2\) and $$\frac{x+1}{x-1}$$",
    placeholder='Some HTML',
    description='Some HTML',
)
```

## Output
```python
out = widgets.Output(layout={'border': '1px solid black'})
```
```python
with out:
    # use output widget
    
# then
# out.clear_output()
```

```python
@out.capture()
def function_with_captured_output():
    print('This goes into the output widget')
    raise Exception('As does this')

function_with_captured_output()
```


## Image
```python
file = open("images/WidgetArch.png", "rb")
image = file.read()
widgets.Image(
    value=image,
    format='png',
    width=300,
    height=400,
)
```


## Button
```python
widgets.Button(
    description='Click me',
    disabled=False,
    button_style='', # 'success', 'info', 'warning', 'danger' or ''
    tooltip='Click me',
    icon='check' # (FontAwesome names without the `fa-` prefix)
)
```

## Play
```python
play = widgets.Play(
    value=50,
    min=0,
    max=100,
    step=1,
    interval=500,
    description="Press play",
    disabled=False
)
slider = widgets.IntSlider()
widgets.jslink((play, 'value'), (slider, 'value'))
widgets.HBox([play, slider])
```

## DatePicker
```python
widgets.DatePicker(
    description='Pick a Date',
    disabled=False
)
```

## ColorPicker
```python
widgets.ColorPicker(
    concise=False,
    description='Pick a color',
    value='blue',
    disabled=False
)
```

## Containers/Layout widgets

### Box
```python
items = [widgets.Label(str(i)) for i in range(4)]
widgets.Box(items)
```

### HBox
```python
items = [widgets.Label(str(i)) for i in range(4)]
widgets.HBox(items)
```

### VBox
```python
items = [widgets.Label(str(i)) for i in range(4)]
left_box = widgets.VBox([items[0], items[1]])
right_box = widgets.VBox([items[2], items[3]])
widgets.HBox([left_box, right_box])
```

### GridBox
```python
items = [widgets.Label(str(i)) for i in range(8)]
widgets.GridBox(items, layout=widgets.Layout(grid_template_columns="repeat(3, 100px)"))
```

### Accordion
Note : the container widgets Accordion and Tab update their selected_index attribute when the user changes which accordion or tab is selected
```python
accordion = widgets.Accordion(children=[widgets.IntSlider(), widgets.Text()], titles=('Slider', 'Text'))
accordion
```

### Tab
Note : the container widgets Accordion and Tab update their selected_index attribute when the user changes which accordion or tab is selected
```python
tab_contents = ['P0', 'P1', 'P2', 'P3', 'P4']
children = [widgets.Text(description=name) for name in tab_contents]
tab = widgets.Tab()
tab.children = children
tab.titles = [str(i) for i in range(len(children))]
tab
```


### Stacked
```python
button = widgets.Button(description='Click here')
slider = widgets.IntSlider()
stacked = widgets.Stacked([button, slider])
stacked  # will show only the button

#dropdown = widgets.Dropdown(options=['button', 'slider'])
#widgets.jslink((dropdown, 'index'), (stacked, 'selected_index'))
#widgets.VBox([dropdown, stacked])
```













```
import numpy as np
import matplotlib.pyplot as plt
import ipywidgets
%matplotlib widget
data = np.random.rand(3000).reshape(100, 6, 5)
fig, ax = plt.subplots();
# short simple version
# ipywidgets.interact(lambda i:ax.imshow(data[i]), i=10);
# longer version
ipywidgets.interact(lambda i:ax.imshow(data[i]), i=ipywidgets.IntSlider(min=0, max=np.shape(data)[0]-1, step=1, value=0));
```

 - display widgets : `IPython.display.display(w)`
 - close widgets : `w.close()`
 - attributes : 
  - value
  - keys
  - description
  - disabled
 
# linking widgets
 - jslink : javascript-link : `mylink = widgets.jslink((a, 'value'), (b, 'value'))`
 
Remove link with `unlink()` method.

# interact

```python
x = widgets.IntSlider(start=0, end=10, step=2)
y = widgets.IntSlider(start=0, end=10, step=2)
def adding(x, y):
    print(f"The sum of {} and {} is {}".format(x, y, x+y))
interact(adding, x=x, y=y)
```

```python
@interact(x=True,y=1.0)
def g(x,y):
    return (x,y)
```

 - customize interact widget : `interact(f,x=widgets.IntSlider(min=-10,max=30,step=1,value=23))`

 - fixed : `from ipywidgets import fixed; interact(g,x=10,y=fixed(20))`

# interactive
By default, interact and interactive call the function for every update of the widgets value.
Similar to interact, but returns a widget instead of juste displaying it.
`w = interactive(f, a=10, b=20)`
To introspect : 
 - w.kwargs
 - w.result

## interact_manual
`foo = interactive(slow_function, {'manual': True}, i=widgets.FloatSlider(min=1e4, max=1e6, step=1e4))
foo`
`
def slow_function(i):
    """
    Sleep for 1 second then print the argument
    """
    from time import sleep
    print('Sleeping...')
    sleep(1)
    print(i)

interact_manual(slow_function,i=widgets.FloatSlider(min=1e4, max=1e6, step=1e4));`

## continuous_update
`interact(slow_function,i=widgets.FloatSlider(min=1e4, max=1e6, step=5e4, continuous_update=False));`

## interactive_ouput
```python
a = widgets.IntSlider()
b = widgets.IntSlider()
c = widgets.IntSlider()

# An HBox lays out its children horizontally
ui = widgets.HBox([a, b, c])

def f(a, b, c):
    # You can use print here instead of display because interactive_output generates a normal notebook 
    # output area.
    print((a, b, c))

out = widgets.interactive_output(f, {'a': a, 'b': b, 'c': c})

display(ui, out)
```


 
https://stackoverflow.com/questions/41667397/interactive-boxplot-with-pandas-and-jupyter-notebook
 