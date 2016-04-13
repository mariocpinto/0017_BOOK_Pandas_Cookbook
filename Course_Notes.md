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
  * To plot a column, use `_DataframeName_[_ColumnName_].plot()`. To plot this as a bar plot, set the keyword `kind=bar`.
  * The `figsize=(_w_,_h_)` keyword can be used to control the size of the figure.

<br>

* [Chapter 2: Selecting data & finding the most common complaint type](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%202%20-%20Selecting%20data%20&%20finding%20the%20most%20common%20complaint%20type.ipynb)
 * Just entering a dataframe name will display a snippet of the contents of the dataframe.
 * To see the first n rows of a dataframe, use `_DataframeName_[:_n_]`. 
 This can be done in column selection. Order of row / column selection does not matter.
 * To select multiple clumns, use `_DataframeName_[ [ _ColumnName1_, _ColumnName2_, ... ] ]`.
 * To count number of occurences of a value in a column and sort by frequency, use `_DataframeName_[_ColumnName_].value_counts()`.

* [Chapter 3: Which borough has the most noise complaints? (or, more selecting data)](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%203%20-%20Which%20borough%20has%20the%20most%20noise%20complaints%20%28or%2C%20more%20selecting%20data%29.ipynb)
 * To filter based on a column value(s), use `_DataframeName_[_criteria_]` 
 where `_criteria_` is for e.g. `_DataframeName_[_ColumnName1_] == _value1_ & _DataframeName_[_ColumnName1_] == _value2_` 
 i.e. a boolean array.
 * The above can be used in conjunction with column and row selection to see a specific subset of the data.
 * The type of a dataframe column is a pandas series, which internally is a numpy array.
 * Selecting elements based on a condition works for numpy arrays as well.
 * One can divide a value count by another (element wise) by using the division operator i.e. `/`.

* [Chapter 4: Find out on which weekday people bike the most with groupby and aggregate](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%204%20-%20Find%20out%20on%20which%20weekday%20people%20bike%20the%20most%20with%20groupby%20and%20aggregate.ipynb)
