.. _objectFunctionality_index:

.. include:: <isonum.txt>

Object-Dependent Functionality
==============================

All of the these functions can be accessed through the menus at the top after selecting the object in the GIFtools tree. The main categories presented here are:


In GIFtools, data, meshes, models and other things are defined as 'objects'. By doing this, GIFtools ensures that the user may only 

Here, we describe the specific set of actions (or methods) which can be applied to each type of object. 


  - :ref:`Data: <objectFunctionalityData>` functions that may be applied to data
  - :ref:`Mesh: <objectFunctionalityMesh>` functions that may be applied to meshes
  - :ref:`Model: <objectFunctionalityModel>` functions that may be applied to models
  - :ref:`Workflow: <objectFunctionalityWorkflow>` functions that may be applied to objects generated through **Create** |rarr| **Workflow**
  - :ref:`Forward Model: <objectFunctionalityFwd>` functions that may be applied to objects generated through **Create** |rarr| **Forward Model**
  - :ref:`Inversions: <objectFunctionalityInv>` functions that may be applied to objects generated through **Create** |rarr| **Inversion**
  - :ref:`Equivalent Source Processing: <objectFunctionalityProcessing>` functions that may be applied to objects generated through **Create** |rarr| **Processing** |rarr| **Equivalent Source Processing**
  - :ref:`Fortran Utility Programs: <objectFunctionalityFortran>` functions that may be applied to objects generated through **Create** |rarr| **Fortran Utility Program**
  - :ref:`Survey: <objectFunctionalitySurvey>` functions that may be applied to objects generated through **Create** |rarr| **Survey**

  .. toctree::
    :hidden:

    data/index
    mesh/index
    model/index
    workflow/index
    forward/index
    inversion/index
    esProcessing/index
    fortran/index
    survey/index

.. _objectFunctionalityMesh2:

Mesh
----

    .. toctree::
        :maxdepth: 1

        mesh/createConstantModel
        mesh/createActiveCellsModel
        mesh/refineOctree
        View in 3D <mesh/viewMesh>        
        Export <mesh/export>

.. _objectFunctionalityModel2:

Model
-----

    .. toctree::
        :maxdepth: 1

        model/createActiveCells
        Set unit name <model/setUnit>
        Perform a simple mathematical operation <model/modelCalculator>
        Add polyhedra from property data <model/addPolyBlock>
        Assign values to air cells <model/assignAirValues>        
        View in 3D, table format, or view statistics <model/viewModel>
        Export <model/export>




.. _objectFunctionalityFwd2:

Create >> Forward
-----------------

    .. toctree::
       :maxdepth: 1

       Set the working directory <forward/setWorkDir>
       Edit options <forward/editOptions>
       Write files <forward/writeAll>
       Run <forward/run>
       Load results <forward/loadResults>
       Copy the item <forward/copyOptions>


.. _objectFunctionalityInv2:

Create >> Inversion
-------------------


    **General functionality:**

    .. toctree::
       :maxdepth: 1

       Set the working directory <inversion/setWorkDir>
       Edit options <inversion/editOptions>
       Write files <inversion/writeAll>
       Run <inversion/run>
       Load results <inversion/loadResults>
       View results <inversion/viewInversion>
       Copy the item <inversion/copyOptions>



       
.. _objectFunctionalityEsrc2:

Create >> Equivalent-Source Processing
--------------------------------------

    **General functionality:**

    .. toctree::
       :maxdepth: 1

       Set the working directory <esProcessing/setWorkDir>
       Edit options <esProcessing/editOptions>
       Write files <esProcessing/writeAll>
       Run <esProcessing/run>
       Load results <esProcessing/loadResults>
       View results <esProcessing/viewInversion>
       Copy the item <esProcessing/copyOptions>

.. _objectFunctionalityFortran2:

Fortran utility program
-----------------------

    **General functionality:**

    .. toctree::
       :maxdepth: 1

       Set the working directory <fortran/setWorkDir>
       Edit options <fortran/editOptions>
       Run <fortran/run>
       Load results <fortran/loadResults>


