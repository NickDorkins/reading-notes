# Class 14: Data Visualization

## [matplotlib tutorial](https://github.com/rougier/matplotlib-tutorial)

## [Intro](https://github.com/rougier/matplotlib-tutorial#id4)

`matplotlib` is probably the single most used Python package for 2D-graphics. It provides both a very quick way to visualize data from Python and publication-quality figures in many formats.

## IPython and the pylab mode

[IPython](http://ipython.org/) is an enhanced interactive Python shell that has lots of interesting features including named inputs and outputs, access to shell commands, improved debugging and much more.

> When we start it with the command line argument `-pylab` (`--pylab` since IPython version 0.12), it allows interactive matplotlib sessions that have Matlab/Mathematica-like functionality.

## pyplot

`pyplot` is an object oriented plotting library, it is modeled closely to Matlab<sup>TM</sup>.

> The majority of plotting commands in `pyplot` have Matlab<sup>TM</sup> analogs with similar arguments. Important commands are explained with interactive examples.

## Simple plot

The first step is to get the data for the sine and cosine functions:

```
import numpy as np

X = np.linspace(-np.pi, np.pi, 256, endpoint=True)
C, S = np.cos(X), np.sin(X)
```
- `X` is now a NumPy array with 256 values ranging from -π to +π (included). 
- `C` is the cosine (256 values) and S is the sine (256 values).

To run the example, you can download each of the examples and run it using:

```
$ python exercice_1.py
```

## Using defaults

Documentation:

- [plot tutorial](http://matplotlib.sourceforge.net/users/pyplot_tutorial.html)
- [plot() command](http://matplotlib.sourceforge.net/api/pyplot_api.html#matplotlib.pyplot.plot)


Matplotlib comes with a set of default settings that allow customizing all kinds of properties. You can control the defaults of almost every property in matplotlib: `figure` `size` and `dpi`, `line width`, `color` and `style`, `axes`, `axis` and `grid properties`, `text` and `font` properties and so on. 

> Matplotlib defaults are good in most cases, but you may want to modify some properties for specific cases.

## Instantiating defaults

Documentation:

- [Customizing matplotlib](http://matplotlib.sourceforge.net/users/customizing.html)


![Default_Settings](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_2.png)

## Changing colors and line widths

Documentation:

- [Controlling line properties](http://matplotlib.sourceforge.net/users/pyplot_tutorial.html#controlling-line-properties)
- [Line API](http://matplotlib.sourceforge.net/api/artist_api.html#matplotlib.lines.Line2D)

**As a first step, we want to have the cosine in blue and the sine in red and a slightly thicker line for both of them. We'll also slightly alter the figure size to make it more horizontal.**

![Thicker Lines w/ Color Change](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_3.png)

Sample Code Block:

```
plt.figure(figsize=(10,6), dpi=80)
plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-")
plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-")
```

## Setting limits

Documentation:

- [xlim() command](http://matplotlib.sourceforge.net/api/pyplot_api.html#matplotlib.pyplot.xlim)
- [ylim() command](http://matplotlib.sourceforge.net/api/pyplot_api.html#matplotlib.pyplot.ylim)

```
plt.xlim(X.min()*1.1, X.max()*1.1)
plt.ylim(C.min()*1.1, C.max()*1.1)
```

> The above code block will create some space to allow the user to view the data without the extra white space on the sides

## Setting ticks

Documentation:

- [xticks() command](http://matplotlib.sourceforge.net/api/pyplot_api.html#matplotlib.pyplot.xticks)
- [yticks() command](http://matplotlib.sourceforge.net/api/pyplot_api.html#matplotlib.pyplot.yticks)
- [Tick container](http://matplotlib.sourceforge.net/users/artists.html#axis-container)
- [Tick locating and formatting](http://matplotlib.sourceforge.net/api/ticker_api.html)

Sample Code Block to show more in depth tick values:
```
plt.xticks( [-np.pi, -np.pi/2, 0, np.pi/2, np.pi])
plt.yticks([-1, 0, +1])
```

## Setting tick labels

Documentation:

- [Working with text](http://matplotlib.sourceforge.net/users/index_text.html)
- [xticks() command](http://matplotlib.sourceforge.net/api/pyplot_api.html#matplotlib.pyplot.xticks)
- [yticks() command](http://matplotlib.sourceforge.net/api/pyplot_api.html#matplotlib.pyplot.yticks)
- [set_xticklabels()](http://matplotlib.sourceforge.net/api/axes_api.html?#matplotlib.axes.Axes.set_xticklabels)
- [set_yticklabels()](http://matplotlib.sourceforge.net/api/axes_api.html?#matplotlib.axes.Axes.set_yticklabels)

This allows the creator to make more in depth labels for the content that they are plotting on a graph.

## Moving spines

Documentation:

- [Spines](http://matplotlib.sourceforge.net/api/spines_api.html#matplotlib.spines)
- [Axis container](http://matplotlib.sourceforge.net/users/artists.html#axis-container)
- [Transformations tutorial](http://matplotlib.sourceforge.net/users/transforms_tutorial.html)

Spines are the lines connecting the axis tick marks and noting the boundaries of the data area. They can be placed at arbitrary positions and until now, they were on the border of the axis. We'll change that since we want to have them in the middle.

![Moved Spines to Center of Data Plot](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_7.png)

Sample Code Block to move the spines to center:

```
ax = plt.gca()
ax.spines['right'].set_color('none')
ax.spines['top'].set_color('none')
ax.xaxis.set_ticks_position('bottom')
ax.spines['bottom'].set_position(('data',0))
ax.yaxis.set_ticks_position('left')
ax.spines['left'].set_position(('data',0))
```

## Adding a legend

Documentation:

- [Legend guide](http://matplotlib.sourceforge.net/users/legend_guide.html)
- [legend() command](http://matplotlib.sourceforge.net/api/pyplot_api.html#matplotlib.pyplot.legend)
- [Legend API](http://matplotlib.sourceforge.net/api/legend_api.html#matplotlib.legend.Legend)

