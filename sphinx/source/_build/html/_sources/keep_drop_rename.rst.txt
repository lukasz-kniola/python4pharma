****************************
Keep, Drop, Rename Variables
****************************

Keep
====
SAS:

.. code-block:: sas

    data class;
      set sashelp.CLASS(keep=NAME SEX AGE);
    run;

Python:

.. code-block:: python

    new_class_df = class_df[['NAME', 'SEX', 'AGE']]

Drop
====
SAS:

.. code-block:: sas

    data class;
      set sashelp.CLASS(drop=HEIGHT WEIGHT);
    run;

Python:

.. code-block:: python

    # copy and drop
    new_class_df = class_df.drop(['HEIGHT', 'WEIGHT'], axis=1)

    # drop in place
    class_df.drop(['HEIGHT', 'WEIGHT'], axis=1, inplace=True)


Rename
======
SAS:

.. code-block:: sas

    data class;
      set sashelp.CLASS(rename=(SEX=GENDER));
    run;

Python:

.. code-block:: python

    # copy and rename
    new_class_df = class_df.rename(columns={'SEX': 'GENDER'})

    # rename in place
    class_df.rename(columns={'SEX': 'GENDER'}, inplace=True)



