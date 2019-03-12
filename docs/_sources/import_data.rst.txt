******************************
Reading and Writing Data Files
******************************

Pandas can read from and write to a number of formats. This includes, but is not limited to CSV, XPT, SAS7BDAT, Excel, JSON, HTML.

Importing Data
==============
To read data into a dataframe:

.. code-block:: python

    dataset1 = pd.read_csv("file.csv")

.. code-block:: python

    dataset2 = pd.read_sas("file.xpt")
    dataset3 = pd.read_sas("file.sas7bdat")

.. Attention:: When SAS file's encoding is different than the system, data will be read in as bytes, which makes is hard to process. Use :literal:`encoding` parameter to avoid this problem.

.. code-block:: python

    dataset2 = pd.read_sas("file.xpt", encoding="utf-8")
    dataset3 = pd.read_sas("file.sas7bdat", encoding="ISO-8859-1")



Exporting Data
==============

Pandas does not support saving data as SAS files, although it is possible to save as XPT, using (`xport <https://pypi.org/project/xport/>`__) module.

Dataframes can be saved as CSV files:

.. code-block:: python

    dataset1.to_csv("new_file.csv")

Another format, native to Python, is pickle:

.. code-block:: python

    dataset1.to_pickle("new_file.pkl")

Feather is an R-compatible format:

.. code-block:: python

    dataset1.to_pickle("new_file.feather")

Each format has some limitations, so depending on the project, different formats may be used.
For more details see Pandas documentation: (`IO Tools (Text, CSV, HDF5, …) <https://pandas.pydata.org/pandas-docs/stable/user_guide/io.html#io-read-csv-table>`__)
