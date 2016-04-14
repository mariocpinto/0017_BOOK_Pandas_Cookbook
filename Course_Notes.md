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

<br>

* [Chapter 3: Which borough has the most noise complaints? (or, more selecting data)](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%203%20-%20Which%20borough%20has%20the%20most%20noise%20complaints%20%28or%2C%20more%20selecting%20data%29.ipynb)
 * To filter based on a column value(s), use `_DataframeName_[_criteria_]` 
 where `_criteria_` is for e.g. `_DataframeName_[_ColumnName1_] == _value1_ & _DataframeName_[_ColumnName2_] == _value2_` 
 i.e. a boolean array.
 * The above can be used in conjunction with column and row selection to see a specific subset of the data.
 * The type of a dataframe column is a pandas series, which internally is a numpy array.
 * Selecting elements based on a condition works for numpy arrays as well.
 * One can divide a value count by another (element wise) by using the division operator i.e. `/`.

<br>

* [Chapter 4: Find out on which weekday people bike the most with groupby and aggregate](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%204%20-%20Find%20out%20on%20which%20weekday%20people%20bike%20the%20most%20with%20groupby%20and%20aggregate.ipynb)
 * To copy a dataframe or a subset, use the `.copy()` method.
 * To get the index of a dataframe use `_DataFrameName_.index`.
 * To get the day of the month and weekday corresponding to a date, use `.day` and `.weekday`.
 * Data can be grouped and aggregated using the `_DataframeName_.groupby(_ColumnName_).aggregate(sum)`.
 * A dataframe index can be overwritten with a new list. Same with the column headers (Set `.columns` to the new list).

<br>

* [Chapter 5: Combining dataframes and scraping Canadian weather data](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%205%20-%20Combining%20dataframes%20and%20scraping%20Canadian%20weather%20data.ipynb)
 * To get rid of rows/columns with missing data, use `dropna()` with appropriate keywords.
 * To get rid of rows/columns, use `drop()` with appropriate keywords.
 * Lots of neat formatting of strings can be done with `.format()`. More [here](https://pyformat.info/).
 * To concatenate data frames, use `.concat(_ListofDataframes_)`. This will concatenate along rows i.e. one under another.
 To concatenate along columns i.e. add columns, add the keyword `axis=1`.
 * To save a dataframe to a csv, use the `.to_csv(_FileName_)` command.

<br>

* [Chapter 6: String operations! Which month was the snowiest?](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%206%20-%20String%20Operations-%20Which%20month%20was%20the%20snowiest.ipynb)
 * To know if entries in a column contain a particular word, use `_DataframeName_[_ColumnName_].str.contains(_SearchString_)`.
 * To make matplotlib plots look prettier, use `matplotlib.pyplot.style.use(_StyleName_)`. Exaples of different style types can be found [here](https://tonysyu.github.io/raw_content/matplotlib-style-gallery/gallery.html).
 To print a list of available styles, use `print plt.style.available`.
 * If we have a time series, the `resample()` method can be used to calculate parameters defined on chunks of data
 ([documentation](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.resample.html)).
 The chunking is defined by the `rule` keyword which takes a string input. Possible values of `rule` are listed [here](http://pandas.pydata.org/pandas-docs/stable/timeseries.html#offset-aliases).
 To define the function to be applied on the cheunks, use `apply(_NumpyMethod_)`.
 * To cast elements of a column to a new type, use `.astype(_NewType_)`.
 * To name a dataframe column with a new column name, use `_DataframeName_[_ColumnName_].name = _NewName_`.
 * To plot multiple columns of a dataframe as separate plots, use the `subplots=True` keyword.

<br>

* [Chapter 7: Cleaning up messy data](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%207%20-%20Cleaning%20up%20messy%20data.ipynb)
 * To find a list of unique entries in a Series, use `.unique()`. It might also help to use this in combination with sorted().
 * To clean up NA values while importing data using read_csv,
 create an array of elements that are to be considered NaNs and pass it along with the `na_values` keyword.
 * To specify the data type of a particular column, create a dictionary with key:column name and value:type
 and pass this along with the `dtype` keyword.
 * To find all string entries whose length exceeds a certain length, use `.str.len() > _number_`.
 * To truncate / slice string entries, use `.str.slice(_StartingIndex-included_, _EndingIndex-Excluded_)`.
 * To set an element to NaN, set it equal to `numpy.nan`.
 * To find string elements starting with a specific set of characters, use `str.startswith(_StartingSequence_)`.
 * To find if entries of a column are not NaNs, use `.notnull()`.

<br>

* [Chapter 8: Parsing Unix timestamps](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%208%20-%20How%20to%20deal%20with%20timestamps.ipynb)
 * To filter out a particular subset of a pandas datetime series, you can write the criteria in terms of strings.
 To clarify: e.g. `popcon['atime'] > '1970-01-01'`.
 * If you have a timestamp in seconds or milliseconds or nanoseconds, then you can just "cast" it to a 'datetime64[the-right-thing]'
 using the `to_datetime()` method (with appropriate parameters) and pandas/numpy will take care of the rest.

<br>

* [Chapter 9 - Loading data from SQL databases](http://nbviewer.ipython.org/github/jvns/pandas-cookbook/blob/master/cookbook/Chapter%209%20-%20Loading%20data%20from%20SQL%20databases.ipynb)
 * To read in a database directly as a pandas object, use `.read_sql(_SELECT statement_, _ConnectionObject_).
 e.g.
 ```python
 con = sqlite3.connect("../data/weather_2012.sqlite")
 df = pd.read_sql("SELECT * from weather_2012 LIMIT 3", con)
 ```
 * To set the primary key (id) to one of the columns of the sql database, 
 use the `index_col=_ColumnName_` as a keyword with `read_sql`.
 It is also possible to pass multiple columns as an id, by passing an list of the column names.
 * To write a dataframe to sql, use `.to_sql()`.
 * One can read from / write to many other formats. The [documentation](http://pandas.pydata.org/pandas-docs/stable/io.html) provides more details.
 
<br>

