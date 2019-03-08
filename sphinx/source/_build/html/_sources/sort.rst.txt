*********
Proc Sort
*********

SAS:

.. code-block:: sas

    proc sort data=sashelp.class out=class;
      by name age;
    run;

Python:

.. code-block:: python

    class_df.sort_values(['NAME', 'AGE'], inplace=True)


