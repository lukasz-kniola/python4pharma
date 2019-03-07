**********************
Set and Merge Datasets
**********************

Set
===

SAS:

.. code-block:: sas
    
    data new;
      set one two;
    run;

Python:

.. code-block:: python

    pd.concat([one, two])
    
    one.append(two)

Merge
=====

SAS:

.. code-block:: sas

    data new;
      merge one(in=i1) two(in=i2);
      by name;
      * inner : if i1 and i2;
      * left  : if i1;
      * right : if i2;
      * outer : if i1 or i2;
    run;

Python:

.. code-block:: python

    new  = pd.merge(one[["NAME", "AGE"]], two, how='left', on="NAME")
    # how = 'inner', 'left', 'right', 'outer'
    
    new  = pd.merge(one, two, how='inner', left_on="NAME", right_on="FirstName")
    
    new  = one.merge(two, how='left', on="NAME")
    
    
