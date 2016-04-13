## Pandas Cookbook: Course Notes

These are my notes as I worked through the [Pandas Cookbook](https://github.com/jvns/pandas-cookbook) by [Julia Evans](http://jvns.ca/).

* [A quick tour of the IPython Notebook](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/A%20quick%20tour%20of%20IPython%20Notebook.ipynb)
  * `Ctrl+Enter` causes in place execution of a cell.
  * `Shift+Enter` causes execution of the cell + jumps to the next cell.
  * `Shift+tab` provides increasing amounts of help.
  * You can use tab completion for function names!
  * There are a number of _magic_ functions inbuilt: `%magic` provides a list and `%quickref` provides a quick reference guide.

<br>

* [Chapter 1: Reading from a CSV](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%201%20-%20Reading%20from%20a%20CSV.ipynb)
  * `%matplotlib inline` will allow plots to be rendered inline in the IPython notebook.
  * `pd.read_csv()` (along with dditional options, can be used to read a csv file into a pandas dataframe.
  * To access a column in a dataframe, use `_DataframeName_[_ColumnName_]`.
  * To plot a column, use `_DataframeName_[_ColumnName_].plot()`. 
  * The `figsize=(_w_,_h_)` keyword can be used to control the size of the figure.

<br>

* [Chapter 2: Selecting data & finding the most common complaint type](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%202%20-%20Selecting%20data%20&%20finding%20the%20most%20common%20complaint%20type.ipynb)
