# Class 11: Reading Data Analysis

## [What is Jupyter Lab?](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html)

**JupyterLab is a next-generation web-based user interface for Project Jupyter.**

JupyterLab enables you to work with documents and activities such as [Jupyter notebooks](https://jupyterlab.readthedocs.io/en/stable/user/notebook.html#notebook), text editors, terminals, and custom components in a flexible, integrated, and extensible manner.

You can [arrange](https://jupyterlab.readthedocs.io/en/stable/user/interface.html#interface) multiple documents and activities side by side in the work area using tabs and splitters. Documents and activities integrate with each other, enabling new workflows for interactive computing, for example:

- [Code Consoles](https://jupyterlab.readthedocs.io/en/stable/user/interface.html#interface) provide transient scratchpads for running code interactively, with full support for rich output. A code console can be linked to a notebook kernel as a computation log from the notebook, for example.

- [Kernel-backed documents](https://jupyterlab.readthedocs.io/en/stable/user/documents_kernels.html#kernel-backed-documents) enable code in any text file (Markdown, Python, R, LaTeX, etc.) to be run interactively in any Jupyter kernel.

- Notebook cell outputs can be [mirrored into their own tab](https://jupyterlab.readthedocs.io/en/stable/user/notebook.html#cell-output-mirror), side by side with the notebook, enabling simple dashboards with interactive controls backed by a kernel.

- Multiple views of documents with different editors or viewers enable live editing of documents reflected in other viewers. For example, it is easy to have live preview of [Markdown](https://jupyterlab.readthedocs.io/en/stable/user/file_formats.html#markdown), [Delimiter-separated Values](https://jupyterlab.readthedocs.io/en/stable/user/file_formats.html#csv), or [Vega/Vega-Lite documents](https://jupyterlab.readthedocs.io/en/stable/user/file_formats.html#vega-lite).

JupyterLab also offers a unified model for viewing and handling data formats. JupyterLab understands many file formats (images, CSV, JSON, Markdown, PDF, Vega, Vega-Lite, etc.) and can also display rich kernel output in these formats. See [File and Output Formats](https://jupyterlab.readthedocs.io/en/stable/user/file_formats.html#file-and-output-formats) for more information.

To navigate the user interface, JupyterLab offers [customizable keyboard shortcuts](https://jupyterlab.readthedocs.io/en/stable/user/interface.html#shortcuts) and the ability to use [key maps](https://jupyterlab.readthedocs.io/en/stable/user/interface.html#editor-keymaps) from vim, emacs, and Sublime Text in the text editor.

JupyterLab [extensions](https://jupyterlab.readthedocs.io/en/stable/user/extensions.html#user-extensions) can customize or enhance any part of JupyterLab, including new themes, file editors, and custom components.

JupyterLab is served from the same [server](https://jupyter-notebook.readthedocs.io/en/stable/) and uses the same [notebook document format](https://nbformat.readthedocs.io/en/latest/) as the classic Jupyter Notebook.

## [Command Cheat Sheet](https://www.edureka.co/blog/wp-content/uploads/2018/10/Jupyter_Notebook_CheatSheet_Edureka.pdf)

## [Jupyter Command Reading](https://jupyterlab.readthedocs.io/en/stable/user/code_console.html#code-console)

---

# [NumPy Tutorial: Data Analysis with Python](https://www.dataquest.io/blog/numpy-tutorial-python/)

[NumPy](http://www.numpy.org/) is a commonly used Python data analysis package. By using NumPy, you can speed up your workflow, and interface with other packages in the Python ecosystem, like [scikit-learn](http://scikit-learn.org/), that use NumPy under the hood. NumPy was originally developed in the mid 2000s, and arose from an even older package called Numeric. This longevity means that almost every data analysis or machine learning package for Python leverages NumPy in some way.

## Lists Of Lists for CSV Data

Before using NumPy, we’ll first try to work with the data using Python and the [csv](https://docs.python.org/3/library/csv.html) package. We can read in the file using the [csv.reader](https://docs.python.org/3/library/csv.html#csv.reader) object, which will allow us to read in and split up all the content from the ssv file.

In the below code, we:

Import the csv library.
Open the winequality-red.csv file.
With the file open, create a new csv.reader object.
Pass in the keyword argument delimiter=";" to make sure that the records are split up on the semicolon character instead of the default comma character.
Call the [list](https://docs.python.org/3/library/functions.html#func-list) type to get all the rows from the file.
Assign the result to wines.

```
import csv
with open('winequality-red.csv', 'r') as f:
    wines = list(csv.reader(f, delimiter=';'))
```

The below code will:

- Extract the last element from each row after the header row.
- Convert each extracted element to a float.
- Assign all the extracted elements to the list qualities.
- Divide the sum of all the elements in qualities by the total number of elements in qualities to the get the mean.

```
qualities =
[float(item[-1]) for item in wines[1:]]
sum(qualities) / len(qualities)
```
> Returned Value: `5.6360225140712945`

## Numpy 2-Dimensional Arrays

With NumPy, we work with multidimensional arrays. We’ll dive into all of the possible types of multidimensional arrays later on, but for now, we’ll focus on 2-dimensional arrays. A 2-dimensional array is also known as a matrix, and is something you should be familiar with. In fact, it’s just a different way of thinking about a list of lists. A matrix has rows and columns. By specifying a row number and a column number, we’re able to extract an element from a matrix.


## Creating A NumPy Array

We can create a NumPy array using the [numpy.array](http://docs.scipy.org/doc/numpy/reference/generated/numpy.array.html) function. If we pass in a list of lists, it will automatically create a NumPy array with the same number of rows and columns. Because we want all of the elements in the array to be float elements for easy computation, we’ll leave off the header row, which contains strings. One of the limitations of NumPy is that all the elements in an array have to be of the same type, so if we include the header row, all the elements in the array will be read in as strings.

## Alternative NumPy Array Creation Methods

There are a variety of methods that you can use to create NumPy arrays. To start with, you can create an array where every element is zero. The below code will create an array with 3 rows and 4 columns, where every element is 0, using [numpy.zeros](http://docs.scipy.org/doc/numpy/reference/generated/numpy.zeros.html):

import numpy as np
empty_array = np.zeros((3,4)) empty_array
It’s useful to create an array with all zero elements in cases when you need an array of fixed size, but don’t have any values for it yet.

You can also create an array where each element is a random number using [numpy.random.rand](https://docs.scipy.org/doc/numpy-1.15.1/reference/generated/numpy.random.randint.html). 

