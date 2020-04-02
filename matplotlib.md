# Version, backend
matplotlib.__version__
matplotlib.get_backend() : returns rcParams['backend']
matplotlib.use('nbagg') : use backend
plt.ion()/off() : activate/deactivate immediately display objects 
%matplotlib backend_name : set backend to nbagg, and plt.ion()

matplotlib.rcsetup.interactive_bk : list interactive backends
matplotlib.rcsetup.non_interactive_bk : list non interactiv backends
matplotlib.rcsetup.all_backends : list all backends
 
# rcParams, style sheet
matplotlib.matplotlib_fname() : rc file path
mpl.rcdefaults() : reset rc file to default
mpl.rc('lines', linewidth=2, linestyle='-.') : dynamic change of rc file
#mpl.rcParams['lines.linewidth'] = 2
#mpl.rcParams['lines.linestyle'] = '-.'

plt.style.use('ggplot') : use ggplot style
plt.style.use('url to style sheet') : use style sheet at url
matplotlib.get_configdir() : config dir
style.use(<style-name>) : use the <style-name>.mplstyle file of the folder mpl_configdir/stylelib
plt.style.available : list available styles

 
# axes creation
fig, axes = plt.subplots(nrows=2, ncols=2) : where axes is a numpy array of Axes objects
fig, ax = plt.subplots()


 
figure():
-          figsize=plt.figaspect(2.0)
-          facecolor=(1, 0, 0, .1)
 
ax.axhline(0, color='gray', linewidth=2)
ax.set_xlim([0.5, 4.5])
ax.set_ylim([-2, 8])
ax.set_title('A Different Example Axes Title')
ax.set_ylabel('Y-Axis (changed)')
ax.set_xlabel('X-Axis (changed)')
equivalent to
ax.set(xlim=[0.5, 4.5], ylim=[-2, 8], title='An Example Axes',
       ylabel='Y-Axis', xlabel='X-Axis')
 
 
plt.show()
 
# DATA argument
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
 
 
 
#Overlapping colorbar
cax = fig.add_axes([0.27, 0.8, 0.5, 0.05])
im = ax.imshow(data, cmap='gist_earth')
fig.colorbar(im, cax=cax, orientation='horizontal')
 

 
 
# axis
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
 
 
ipympl built on top of ipywidgets, and set with %matplotlib widget
 
https://matplotlib.org/gallery/#embedding-matplotlib-in-graphical-user-interfaces
 
https://github.com/matplotlib/GettingStarted/blob/master/notebooks/06-interactive.ipynb
 
 
https://github.com/matplotlib/matplotlib/blob/0ea20132e306c4607617b61dca7143ea34d30ad0/lib/matplotlib/units.py
https://github.com/matplotlib/matplotlib/blob/e70c9d29a359302ed4046c26a74bf566702e1b6c/lib/matplotlib/tests/test_units.py
https://github.com/matplotlib/matplotlib/blob/bfda3a47834283436f20a1c79bd1199e2d774201/examples/units/evans_test.py
https://github.com/hgrecco/pint/blob/master/pint/matplotlib.py
 
 
    
https://stackoverflow.com/questions/21271195/can-i-use-matplotlib-units-to-switch-between-the-units-displayed-on-a-graph
 
https://github.com/yt-project/unyt
 