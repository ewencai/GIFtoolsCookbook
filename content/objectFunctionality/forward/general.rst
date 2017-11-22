.. _objectFunctionalityFwdGeneral:

.. include:: <isonum.txt>

General Functionality
=====================

.. _objectFwdWorkingDirectory:

Set and View Working Directory
------------------------------

The working directory determines where GIFtools will output the files required to run the forward modeling code. The working directory is typically set when the user creates a forward modeling object. However, the user may choose to change the working directory at any time. The working directory can be set or view through"

	- **_________ forward modeling** |rarr| **Working directory**


.. figure:: ../../../images/simpleFwdMenu.png
    :align: center
    :width: 400

**NOTE:** The shortcut for the functionality is ``control + d``.


.. _objectFwdEditOptions:

Edit Options
------------

Here, the user sets the properties, mesh, model, etc... associated with the forward model. Depending on the forward modeling that is being done (gravity, magnetics, FEM, etc...), the set of properties and associate objects may change. Under each forward modeling type, there is a section which describes the contents of *Edit Options*. For any forward modeling type, this functionality can be access through:

**[Forward class]** |rarr| **Edit options**

.. figure:: ../../../images/simpleFwdMenu.png
    :align: center
    :width: 400

.. _objectFwdSelectVersion:

Select Version
--------------

For any forward modeling type, this functionality can be access through:

**[Forward class]** |rarr| **Select version**

.. figure:: ../../../images/simpleFwdMenu.png
    :align: center
    :width: 400

.. _objectFwdCopyFwd:

Copy a Forward Modeling Item
----------------------------

Once the forward model has run and the results have been loaded, GIFtools does not allow the straight copying of the forward model item (it has been "archived" and becomes a folder). It does, however, allow you to copy the options that were chosen for the forward modeling to a new one. Click on the forward model item, select the menu showing its class (e.g., ``MAGforward`` or ``GRAVforward``):

**[Forward class]** |rarr| **Copy options**

.. figure:: ../../../images/simpleFwdMenu.png
    :align: center
    :width: 400

.. _objectFwdWriteAll:

Write Forward Model Files to Directory
--------------------------------------

Prior to running a forward model, the user must write the appropriate files to the working directory. Click on the forward item, select the menu showing its class (e.g., ``MAGforward``):

**[Forward class]** |rarr| **Write files**

.. figure:: ../../../images/simpleFwdMenu.png
    :align: center
    :width: 400

.. _objectFwdRun:

Run a Forward Model
-------------------

Prior to running the forward model, the user must :ref:`write <objectFwdWriteAll>` the files required to the working directory. Click on the inversion item, select the menu showing its class (e.g., ``MAGforward``):

**[Forward class]** |rarr| **Run [forward name]**

.. figure:: ../../../images/simpleFwdMenu.png
    :align: center
    :width: 400

.. _objectFwdLoadAll:

Load Forward Modeling Results
-----------------------------

Once the forward modelling has run, the user can load the predicted data by clicking on the inversion item, selecting the menu showing its class (e.g., ``MAGforward``), and load predicted data:

**[Forward class]** |rarr| **Load predicted data**


.. figure:: ../../../images/simpleFwdMenu.png
    :align: center
    :width: 400



