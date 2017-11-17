.. _objectFunctionality_index:

Object-Dependent Functionality
==============================

All of the these functions can be accessed through the menus at the top after selecting the object in the GIFtools tree. The main categories presented here are:


In GIFtools, data, meshes, models and other things are defined as 'objects'. By doing this, GIFtools ensures that the user may only 

Here, we describe the specific set of actions (or methods) which can be applied to each type of object. 




- Data
- Mesh
- Model


.. _objectFunctionalityData:

Data
----

General Functionality
^^^^^^^^^^^^^^^^^^^^^

    .. toctree::
        :maxdepth: 2

        data/general/dataType
        data/general/dataManipulation
        data/general/dataVisualization

Magnetics
^^^^^^^^^

    .. toctree::
        :maxdepth: 1

        Assign / Edit inducing field <data/editFieldParams>
        Remove IGRF <data/removeIGRF>
        Add Gaussian noise <data/addGaussianNoise>
        Calculate a polynomal trend <data/polyTrend>


DC/IP
^^^^^
    
    .. toctree::
        :maxdepth: 1

        Add topography to locations <data/applyTopo>
        Apparent resitivity to/from normalized voltage <data/dcipGeoFactor>
        Project DC/IP 3D data onto a 2D lines for DCIP2D inversion <data/dcip3Dto2D>

Electromagnetics (EM)
^^^^^^^^^^^^^^^^^^^^^

    .. toctree::
        :maxdepth: 1

        Extract time / frequency data <data/emTimeExtract>
        View / edit times or frequencies <data/emViewTime>

.. _objectFunctionalityMesh:

Mesh
----

    .. toctree::
        :maxdepth: 1

        mesh/createConstantModel
        mesh/createActiveCellsModel
        mesh/refineOctree
        View in 3D <mesh/viewMesh>        
        Export <mesh/export>

.. _objectFunctionalityModel:

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




.. _objectFunctionalityFwd:

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


.. _objectFunctionalityInv:

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



       
.. _objectFunctionalityEsrc:

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

.. _objectFunctionalityFortran:

Fortran utility program
-----------------------

    **General functionality:**

    .. toctree::
       :maxdepth: 1

       Set the working directory <fortran/setWorkDir>
       Edit options <fortran/editOptions>
       Run <fortran/run>
       Load results <fortran/loadResults>


