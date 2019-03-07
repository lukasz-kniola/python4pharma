*********
Proc Sort
*********

Standard Sort
=============

SAS:

.. code-block:: sas

    proc sort data=sashelp.class out=class;
      by age;
    run;

Python:

.. code-block:: python

    new_class_df = class_df.sort_values('AGE')

Sort nodupkey
=============

SAS:

.. code-block:: sas

    * Find all unique age values, keep records with lowest height and weight values *;
    * Option 1 *;
    proc sort data=sashelp.class out=ages;
      by age height weight;
    proc sort nodupkey;
      by age;
    run
    
    * Option 2 *;
    proc sort data=sashelp.class out=ages;
      by age height weight;
    data ages;
      set ages;
      by age;
      if first.age;
      * can also keep last record        : if last.age;
      * or remove all non-unique records : if not (first.age and last.age);
    run


Python:

.. code-block:: python

    ages = class_df.sort_values(['AGE','HEIGHT','WEIGHT').drop_duplicates(subset=(["AGE"]), keep='first')
    # use keep='last' to keep last record, or False to drop all duplicate records
