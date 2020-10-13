# ressources
- https://towardsdatascience.com/interactive-pivot-tables-in-jupyter-notebook-fc74bad8aa67
- Github repo of jupyter wrapper: https://github.com/nicolaskruchten/jupyter_pivottablejs
- Github repo of pivottable.js https://github.com/nicolaskruchten/pivottable
- Example in jupyter : https://github.com/nicolaskruchten/jupyter_pivottablejs/blob/master/example/jupyter_pivottablejs_example.ipynb
- Author post release : http://nicolas.kruchten.com/content/2015/09/jupyter_pivottablejs/
- Pypi : https://pypi.org/project/pivottablejs/


# Usage
Installation : `pip install pivottablejs`  
Then :
```python
import pivottablejs
import pandas as pd
import numpy as np
db = pd.read_csv("db.csv")
from pivottablejs import pivot_ui
```
then to run in notebook : 
```python
pivot_ui(db, rendererOptions={"d3": {"size": {"height": 400, "width": 600}}})
```
or to run in a separate tab : 
```python
pivot_ui(db, outfile_path="y.html", url="http://localhost/y.html")
```