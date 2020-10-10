# Ressources
 - Official doc :http://ipywidgets.readthedocs.io/en/latest/index.html
 - Tutorial : https://github.com/jupyter-widgets/tutorial
 - Gitter lobby : https://gitter.im/jupyter-widgets/Lobby
 - Examples : https://github.com/JuanCab/AstroInteractives
 - Tutorial : https://github.com/jupyter-widgets/ipywidgets/blob/master/docs/source/examples/Index.ipynb
 - Widgets list : https://github.com/jupyter-widgets/tutorial/blob/master/notebooks/reference_guides/complete-ipywidgets-widget-list.ipynb
 - Flexbox model : https://github.com/jupyter-widgets/tutorial/blob/master/notebooks/reference_guides/guide-flex-box.ipynb
 - Gridbox model : https://github.com/jupyter-widgets/tutorial/blob/master/notebooks/reference_guides/guide-grid-box.ipynb
 - Building a df-reader tutorial :https://medium.com/analytics-vidhya/python-data-projects-data-analysis-ui-reinforced-by-ipywidgets-d680493464b8
 - List of keys and style_keys:https://github.com/jupyter-widgets/tutorial/blob/master/notebooks/Table_of_widget_keys_and_style_keys.ipynb
 - Tutorial : https://towardsdatascience.com/bring-your-jupyter-notebook-to-life-with-interactive-widgets-bc12e03f0916
 - Tutorial/intro : https://kapernikov.com/ipywidgets-with-matplotlib/
 - Example of widget app :
   - Drawing pad : https://github.com/ocoudray/jupyter-drawing-pad
   - Sidecar : https://github.com/jupyter-widgets/jupyterlab-sidecar
   - Ipyvuetify : https://github.com/mariobuikhuizen/ipyvuetify
   - Df reader : https://github.com/finos/perspective
   - Widget example : https://hub.gke2.mybinder.org/user/geoscixyz-em-apps-orf54c5h/notebooks/index.ipynb
   - Tutorial : https://kapernikov.com/ipywidgets-with-matplotlib/
   - https://ipython-books.github.io/33-mastering-widgets-in-the-jupyter-notebook/



# quickstart 

```python
import ipywidgets as widgets
```

Common widget attributes : 
- `value`
- `keys`
- `description`
- `disabled`
- `layout` : a `Layout` object for generic css properties
- `style` : a widget-specific style object for specific styling
- `continuous_update` : kwarg to restrict execution on mouse release on most sliders and text widget


A list of common widget attributes can be found [here](https://github.com/jupyter-widgets/tutorial/blob/master/notebooks/Table_of_widget_keys_and_style_keys.ipynb).

Common widget methods : 
 - link widget's values : `mylink = widgets.link((a, 'value'), (b, 'value'))`
 - observe widget attribute : `w.observe(function_to_run_on_change, names="widget_attribute_to_observe")`
 - display widgets : `IPython.display.display(w)`
 - close widgets : `w.close()`


# Interact, Interactive, Interactive manual and Interactive output

 - `interact` : only display inputs widgets and output
 - `interactive` : same but returns a widget
 - `interactive_manual` : same as interact, but with a button to update results
 - `interactive_output` : One liner to create a widget output that displays the output of an interactive function


## Interact

Basic usage : 

```python
x = widgets.IntSlider(start=0, end=10, step=2)
y = widgets.IntSlider(start=0, end=10, step=2)
def adding(x, y):
    print(f"The sum of {} and {} is {}".format(x, y, x+y))
interact(adding, x=x, y=y)
```

As decorator :

```python
@interact(x=True,y=1.0)
def g(x,y):
    return (x,y)
```


## Interactive

Similar to interact, but returns a widget instead of juste displaying it.

`w = interactive(f, a=10, b=20)`
To introspect : 
 - w.kwargs
 - w.result

## interact_manual

By default, interact and interactive call the function for every update of the widgets value. Interact_manual is an option to pass to create a button to update results.

```python
foo = interactive(slow_function, {'manual': True},
                  i = widgets.FloatSlider(min=1e4, max=1e6, step=1e4))
foo
```

```python
def slow_function(i):
    """
    Sleep for 1 second then print the argument
    """
    from time import sleep
    print('Sleeping...')
    sleep(1)
    print(i)

interact_manual(slow_function,i=widgets.FloatSlider(min=1e4, max=1e6, step=1e4));`
```


## interactive_ouput
One liner to create a widget output that displays the output of an interactive function. Allows to control the inputs widgets, as it only creates the widget for the output.

```python
wa = widgets.IntSlider()
wb = widgets.IntSlider()
wc = widgets.IntSlider()

# An HBox lays out its children horizontally
ui = widgets.HBox([a, b, c])

def f(a, b, c):
    # You can use print here instead of display because interactive_output generates a normal notebook 
    # output area.
    print((a, b, c))

out = widgets.interactive_output(f, {'a': wa, 'b': wb, 'c': wc})

display(ui, out)
```


# Linking and observing widgets
Using link is great if no transformation of the values is needed. observe is useful if some kind of calculation needs to be done with the values or if the values that are related have different types.

## Link
 - to link properties : `mylink = widgets.link((a, 'value'), (b, 'value'))`
 - jslink : javascript-link : `mylink = widgets.jslink((a, 'value'), (b, 'value'))`
 - dlink : directionnal linkg
 - djslink : directionnal java-script side linking
Remove link with `unlink()` method.

## Observe
The callback registered must have the signature `handler(change)` where change is a dictionary holding the information about the change. The change has :

 - owner : the HasTraits instance
 - old : the old value of the modified trait attribute
 - new : the new value of the modified trait attribute
 - name : the name of the modified trait attribute.

```python
slider = widgets.FloatSlider(
    value=7.5,
    min=5.0,
    max=10.0,
    step=0.1,
    description='Input:',
)

# Create non-editable text area to display square of value
square_display = widgets.HTML(description="Square: ",
                              value='{}'.format(slider.value**2))

# Create function to update square_display's value when slider changes
def update_square_display(change):
    square_display.value = '{}'.format(change.new**2)
    
slider.observe(update_square_display, names='value')

# Put them in a vertical box
widgets.VBox([slider, square_display])

```


```python
int_range = widgets.IntSlider()
output2 = widgets.Output()

display(int_range, output2)

def on_value_change(change):
    output2.clear_output(wait=True)

    old = change['old']
    new = change['new']

    with output2:
        print(f'The value was {old} and is now {new}')

int_range.observe(on_value_change, names='value')
```


# Layout and styling:

Difference between layout and style : 

 - A layout can be shared by multiple different widgets
 - A style is widget-specific

```python
from ipywidgets import Button, Layout, ButtonStyle
my_layout = Layout(width='50%', height='80px',
                   border='2px dotted blue')
my_buttont_style = ButtonStyle(button_color = 'lightgreen')
b1 = Button(description='(50% width, 80px height) button',
           layout=my_layout,
           style=my_button_style)
```


## Layout

A `Layout` object has several attributes that can be object-oriented-changed or initialized at creation like `Layout(width='50%')`.

- Sizes
   - `height`(50%, 50px)
   - `width`
   - `max_height`
   - `max_width`
   - `min_height`
   - `min_width`
- Display
   - `visibility`
   - `display`
   - `overflow`
   - `overflow_x` (deprecated in 7.5, use overflow instead)
   - `overflow_y` (deprecated in 7.5, use overflow instead)
- Box model
   - `border`
   - `margin` or margin = « 100px 240px 0px 9px » for top, right bottom left
   - `padding`
- Positioning
   - `top`
   - `left`
   - `bottom`
   - `right`
- Image/media
   - `object_fit`
   - `object_position`
- Flexbox
   - `order`
   - `flex_flow`
   - `align_items`
   - `flex`
   - `align_self`
   - `align_content`
   - `justify_content`
   - `justify_items`
- Grid layout
   - `grid_auto_columns`
   - `grid_auto_flow`
   - `grid_auto_rows`
   - `grid_gap`
   - `grid_template_rows`
   - `grid_template_columns`
   - `grid_template_areas`
   - `grid_row`
   - `grid_column`
   - `grid_area`
 
## Style

The accessible attribute for a widget-style are in its `keys` attribute : `b2.style.keys`

List of style keys :

- IntSlider has style keys: `description_width`, `handle_color`
- FloatSlider has style keys: `description_width`, `handle_color`
- IntRangeSlider has style keys: `description_width`, `handle_color`
- FloatRangeSlider has style keys: `description_width`, `handle_color`
- IntProgress has style keys: `bar_color, description_width`
- FloatProgress has style keys: `bar_color, description_width`
- BoundedIntText has style keys: `description_width`
- BoundedFloatText has style keys: `description_width`
- IntText has style keys: `description_width`
- FloatText has style keys: `description_width`
- ToggleButton has style keys: `description_width`
- Checkbox has style keys: `description_width`
- Valid has style keys: `description_width`
- Dropdown has style keys: `description_width`
- RadioButtons has style keys: `description_width`
- Select has style keys: `description_width`
- SelectionSlider has style keys: `description_width`
- SelectionRangeSlider has style keys: `description_width`
- ToggleButtons has style keys: `button_width`, `description_width`, `font_weight`
- SelectMultiple has style keys: `description_width`
- Text has style keys: `description_width`
- Textarea has style keys: `description_width`
- Label has style keys: `description_width`
- HTML has style keys: `description_width`
- HTMLMath has style keys: `description_width`
- Image has style keys:
- Button has style keys: `button_color`, `font_weight`
- Play has style keys: `description_width`
- DatePicker has style keys: `description_width`
- ColorPicker has style keys: `description_width`
- Box has style keys:
- HBox has style keys:
- VBox has style keys:
- Accordion has style keys:
- Tab has style keys:


# Widgets list
To create a browser of available widgets:
```python
import ipywidgets as widgets
from widget_org import organized_widgets, list_overview_widget
groups = organized_widgets(organize_by='ui')
help_url_base='reference_guides/complete-ipywidgets-widget-list.ipynb'
list_overview_widget(groups, columns=2,
                     min_width_single_widget=200, help_url_base=help_url_base)
```
Or use : `import ipywidgets as widgets; print(dir(widgets))`

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

## TwoByTwoLayout
```python
from ipywidgets import TwoByTwoLayout, Button, Layout
TwoByTwoLayout(top_left=Button(description="Top left"),
               top_right=Button(description="Top right"),
               bottom_left=Button(description="Bottom left"),
               bottom_right=Button(description="Bottom right"))
```
## AppLayout
```python
from ipywidgets import AppLayout, Button, Layout
header        = Button(description="Header",
                       layout=Layout(width="auto",
                                     height="auto"))
left_sidebar  = Button(description="Left Sidebar",
                       layout=Layout(width="auto",
                                     height="auto"))
center        = Button(description="Center",
                       layout=Layout(width="auto",
                                     height="auto"))
right_sidebar = Button(description="Right Sidebar",
                       layout=Layout(width="auto",
                                     height="auto"))
footer        = Button(description="Footer",
                       layout=Layout(width="auto",
                                     height="auto"))
AppLayout(header=header,
          left_sidebar=left_sidebar,
          center=center,
          right_sidebar=right_sidebar,
          footer=footer)
```
 
## GridSpecLayout
```python
from ipywidgets import GridspecLayout, Button, Layout
grid = GridspecLayout(4, 3)
for i in range(4):
    for j in range(3):
        grid[i, j] = Button(layout=Layout(width='auto',
                                          height='auto'))
grid
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

 
https://stackoverflow.com/questions/41667397/interactive-boxplot-with-pandas-and-jupyter-notebook
 
 

 
 
