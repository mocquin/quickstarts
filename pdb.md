# pdb
 
# calls
 - in the code, import module and set trace : `import pdf; pdf.set_trace()`
 - in the code, insert breakpoint with the built-in function (python>=3.7): `breakpoint()`
 - in shell, call the pdb module with the script as argument : `python –m pdb toto.py`
 - post-mortem : import pdb; pdb.pm()
 - in notebooks : from IPython.core.debugger import set_trace; set_trace()
 - open an Ipython session at runtime : insert `from IPython import embed; embed()` at breakpoint spot, then quit Ipython (will restore execution of source code)
 - use ipdb : import ipdb; ipdb.set_trace()
 - ipython magic line run with –d :
  - %run -d filename.py
  - %run -d  -b42 filename.py to start debugging at line 42
  - %run -d -b myotherfile.py:42 myscript.py
 - Ipython : post mortem debugging : run `%debug` after crash (equivalent to import pdb; pdb.pm())
 - Toggle automatic debugging : %pdb : will enable/disable opening debugger at each exception
 
# commands
 - ` l` ou `list` : list code source
 - ` l 3,10` : list code source from line 3 to 10
 - `ll` ou `long list`
 - ` p` ou `print` : Print the value of an expression.
 - ` p toto` : print the toto variable
 - ` pp` ou ` prettyprint ` : Pretty-print the value of an expression.
 - `n  `next` : go to next line : Continue execution until the next line in the current function is reached or it returns.
 - `s  `step` : step into next frame : Execute the current line and stop at the first possible occasion (either in a function that is called or in the current function).
 - ` Until ` : skip to end of loop : Continue execution until the line with a number greater than the current one is reached. With a line number argument, continue execution until a line with a number greater or equal to that is reached.
 - `r` ou `return` : skip to end of function
 - ` b` : set un breakpoint  : With no arguments, list all breaks. With a line number argument, set a breakpoint at this line in the current file.
 - ` b 16`  : set breakpoint on line 16
 - ` cl` ou `clear` : clear breakpoint
 - ` c` ou `continue` : skip to next breakpoint  : Continue execution and only stop when a breakpoint is encountered.
 - ` interact` : opens interactive mode
 -  `q` ou `quit` : quit debugger
 - `w` : Print a stack trace, with the most recent frame at the bottom. An arrow indicates the current frame, which determines the context of most commands
 - `h` : help
 - `h continue` : help on command
 - `h pdb` : full pdb doc
 - `display expr` : Display the value of expression if it changed, each time execution stops in the current frame. Without expression, list all display expressions for the current frame.
 - `undisplay expr` : Do not display expression any more in the current frame. Without expression, clear all display expressions for the current frame.
 - Args : if you are inside a function it prints the arguments
 - u : Move the current frame one level up in the stack trace (to an older frame).
 - d : Move the current frame one level down in the stack trace (to a newer frame).
 
 
## interactive mode
Exit interacvtive console : CTRL+D (sends EOF)
 
## breakpoint() in python>3.7
PYTHONBREAKPOINT=0 : disable breakpoints
See https://www.python.org/dev/peps/pep-0553/
 
# ressources
 
## tutorials
https://realpython.com/python-debugging-pdb/
https://switowski.com/blog/ipython-debugging
 
## debuger packages
- pdb : https://docs.python.org/3/library/pdb.html
- pudb : https://pypi.org/project/pudb/
- pdb++ : https://pypi.org/project/pdbpp/
- ipdb : https://pypi.org/project/ipdb/
 
## youtube
- pudb : https://www.youtube.com/watch?v=I6yEW9DCPMA
