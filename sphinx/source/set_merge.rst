**********************
Set and Merge Datasets
**********************

Set
===


Merge
=====

Keep
====
SAS:

.. code-block:: sas

    data new_class;
      merge sashelp.class(in=i1) class_detail(in=i2);
      by name;
      * inner : if i1 and i2;
      * left  : if i1;
      * right : if i2;
      * outer : if i1 or i2;
    run;

Python:

.. code-block:: python

    new_class_df  = pd.merge(class_df[["USUBJID", "AGE"]], class_detail, how='left', on="NAME")
    # how = 'inner', 'left', 'right', 'outer'
    
    new_class_df  = pd.merge(class_df, class_detail, how='inner', left_on="NAME", right_on="FirstName")
    
    new_class_df  = class_df.merge(class_detail, how='left', on="NAME")
    
    
