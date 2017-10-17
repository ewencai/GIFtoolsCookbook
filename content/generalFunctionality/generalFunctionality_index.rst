.. _generalFunctionality_index:

General functionality
=====================

All of the these functions can be accessed through the menus at the top after selecting the object in the GIFtools tree. The main categories presented here are:

- :ref:`project`
- :ref:`data`
- :ref:`mesh`
- :ref:`model`
- :ref:`fwd`
- :ref:`inv`
- :ref:`mb`
- :ref:`esrc`
- :ref:`util`
- :ref:`surv`


.. _project:

Project
-------

    .. toctree::
        :maxdepth: 1
        
        Load <project/load>
        Load a recent project <project/loadRecent>
        Add an existing project <project/addProject>        
        Save <project/save>
        Auto-save functionality <project/autoSave>
        Set the working directory <project/setWorkDir>
        Set the starting directory <project/setStartingDir>
        Set the number of OpenMP threads <project/setOMPthreads>        
        Find the version number <project/about>


.. _data:

Data
----

    **General functionality:**

    .. toctree::
        :maxdepth: 1

        data/editDataHeaders
        Delete columns <data/deleteDataColumns>
        Create topography <data/dataCreateTopo>
        Create 3D mesh <data/dataCreateMesh>
        Downsample <data/downsample>        
        Set input/output (i/o) headers <data/setioHeaders>
        Assign uncertainties <data/assignUncertainties>
        Perform a simple mathematical operation <data/constantCalculator>
        Perform column-to-column mathematical operation <data/columnCalculator>
        Add Gaussian noise <data/addNoise>
        Combine like objects <data/combineData>
        Delete data outside of a mesh <data/meshBasedRemoval>
        Calculate a polynomal trend <data/polyTrend>
        View in 3D, table format, or view statistics <data/viewData>
        Export <data/export>


    **Magnetics:**

    .. toctree::
        :maxdepth: 1

        Assign / Edit inducing field <data/editFieldParams>
        Remove IGRF <data/removeIGRF>


    **DC/IP:**
    
    .. toctree::
        :maxdepth: 1

        Add topography to locations <data/applyTopo>
        Apparent resitivity to/from normalized voltage <data/dcipGeoFactor>
        Project DC/IP 3D data onto a 2D lines for DCIP2D inversion <data/dcip3Dto2D>

    **EM:**

    .. toctree::
        :maxdepth: 1

        Extract time / frequency data <data/emTimeExtract>
        View / edit times or frequencies <data/emViewTime>

.. _mesh:

Mesh
----

    .. toctree::
        :maxdepth: 1

        mesh/createConstantModel
        mesh/createActiveCellsModel
        mesh/refineOctree
        View in 3D <mesh/viewMesh>        
        Export <mesh/export>

.. _model:

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


.. _fwd:

Forward modelling
-----------------

    **Creating an object:**
   
    .. toctree::
        :maxdepth: 1

        Magnetics <forward/mag3d>
        Gravity <forward/grav3d>
        Gravity gradiometry <forward/ggFwd>
        DC/IP <forward/dcipFwd>
        Frequency-domain EM <forward/femFwd>
        Time-domain EM <forward/temFwd>

    **General functionality:**

    .. toctree::
       :maxdepth: 1

       Set the working directory <forward/setWorkDir>
       Edit options <forward/editOptions>
       Write files <forward/writeAll>
       Run <forward/run>
       Load results <forward/loadResults>
       Copy the item <forward/copyOptions>

.. _inv:

Inversion
---------

    **Creating an object:**

    .. toctree::
        :maxdepth: 1
        
        Through a workflow <inversion/inversionWorkflow>
        Magnetics <inversion/mag3d>
        Gravity <inversion/grav3d>
        Gravity gradiometry <inversion/ggInv>
        DC/IP <inversion/dcipInv>        
        Frequency-domain EM <inversion/femInv>
        Time-domain EM <inversion/temInv>
        Natural-source EM <inversion/mtz3d>

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


.. _mb:

ModelBuilder module
-------------------

 .. toctree::
        :maxdepth: 1

        Create modelBuilder <modelBuilder/createModelBuilder>


       
.. _esrc:

Equivalent-source processing
----------------------------

    **Creating an object:**

    .. toctree::
        :maxdepth: 1

        Gravity <esProcessing/grav3d>
        Magnetics <esProcessing/mag3d>

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

.. _util:

Fortran utility programs
------------------------

    **Creating octree mesh:**

    .. toctree::
        :maxdepth: 1

        E3D <utilityCodes/e3doctreeMesh>
        E3DMT (and ZTEM) <utilityCodes/e3dmtoctreeMesh>
        TD (1 mesh) <utilityCodes/tdoctreeMesh>
        TD (tiled) <utilityCodes/tdoctreeMeshTiled>
        DC (and IP) <utilityCodes/dcoctreeMesh>
        Gravity (PDE) <utilityCodes/gravoctreeMesh>
        Magnetics (PDE) <utilityCodes/magoctreeMesh>

    **Interpolate models**   

    .. toctree::
    	:maxdepth: 1

    	3D mesh to 3D mesh <utilityCodes/interpolateModel>    
    	3D mesh to octree <utilityCodes/mesh3DToOctree>
    	Octree to mesh3D <utilityCodes/octreeToMesh3D>
    	Octree to octree <utilityCodes/octreeToOctree>

    **Octree utilities**

    .. toctree::
    	:maxdepth: 1

    	Regularize octree mesh <utilityCodes/regularizeOctreeMesh>
    	Refine octree mesh <utilityCodes/refineOctreeMesh>
    	Create surface weights <utilityCodes/createSurfaceWeights>
    	Create interface weights <utilityCodes/createInterfaceWeights>
    	Export cell centre locations <utilityCodes/exportCellCentres>
        Create surface electrodes (DC/IP) <utilityCodes/createElectrodes>

    **General functionality:**

    .. toctree::
       :maxdepth: 1

       Set the working directory <utilityCodes/setWorkDir>
       Edit options <utilityCodes/editOptions>
       Run <utilityCodes/run>
       Load results <utilityCodes/loadResults>

.. _surv:

Survey
------

    .. toctree::
        :maxdepth: 1
        
        Create a simple ground or airborne survey <survey/simpleSurvey>


