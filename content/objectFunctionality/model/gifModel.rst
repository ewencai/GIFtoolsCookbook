.. _objectFunctionalityGifModel:

.. include:: <isonum.txt>

Functionality for GIF Models
============================

.. _objectFunctionalityUnitName:

Set Unit Name for the Model
---------------------------

To set the model unit name, select the GIFmodel object then the menu:

**GIFmodel** |rarr| **Edit** |rarr| **Set unit name** 


.. figure:: ../../../images/modelEditMenu.png
    :align: center
    :width: 400


**NOTE** This will *not* change the values of the units (use the :ref:`simple calculator<objectFunctionalityMathSimple>` to change units)! Simply the unit name.

.. _objectFunctionalityMathSimple:

Perform Simple Mathematical Operations on Model Values
------------------------------------------------------

To perform a simple mathematical operation (i.e., change units), select the GIFmodel object then the menu:

**GIFmodel** |rarr| **Edit** |rarr| **Calculate** |rarr| **Simple calculator** 


.. figure:: ../../../images/modelEditMenu.png
    :align: center
    :width: 400


.. _objectFunctionalityMathModel:

Perform Mathematical Operations Involving Another Model
-------------------------------------------------------

To perform a mathematic operations involving another model (i.e., sum the values), select the GIFmodel object then the menu:

**GIFmodel** |rarr| **Edit** |rarr| **Calculate** |rarr| **Model calculator** 


.. figure:: ../../../images/modelEditMenu.png
    :align: center
    :width: 400



.. _objectFunctionalityAddPolyhedra:

Add Rectangular Block and Polyhedra-Based Structures 
----------------------------------------------------

The property data locations or locations based on data values may be used. Either convex or non-convex polyhedra may be calculated. Select the GIFmodel object then the menu:

- Block: **GIFmodel** |rarr| **Edit** |rarr| **Add** |rarr| **Rectangular Block** 

- Convex: **GIFmodel** |rarr| **Edit** |rarr| **Add** |rarr| **convex polyhedron from PROPdata** 

- Non-convex: **GIFmodel** |rarr| **Edit** |rarr| **Add** |rarr| **non-convex polyhedron from PROPdata** 

.. figure:: ../../../images/modelEditMenu.png
    :align: center
    :width: 400

 
**Prerequisites**

A property data (PROPdata) item must be ref:`imported <importProp>`.


.. _objectFunctionalityModReplaceValue:

Replace Value
-------------

This functionality allows the user to change the physical property value of cells within a GIF model based on their current value. This functionality is accessed through:

**GIFmodel** |rarr| **Edit** |rarr| **Replace value**

The following fields are then filled in:

	- **Old value:** approximate value for cells whose physical property will be replaced
	- **New value:** new physical property value for cells being replaced
	- **Tolerance:** The extent at which physical property values may differ from *old value* and be replace by *new value*




