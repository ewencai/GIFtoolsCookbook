.. _coreFunctionality_index:

Core/Basic Functionality
========================

The core/basic GIFtools functionality is always accessible through several drop-down menus. This functionality allows the user to manage GIF projects, import data files and create various GIF objects.

- :ref:`project`: Loading, saving and managing GIF projects
- :ref:`import`: Importing data, mesh, model and other files to GIFtools
- :ref:`create`: Create various GIF objects
- :ref:`util`: Create GIF objects through the use of Fortran utility programs
- :ref:`surv`: Create a survey object

.. figure:: ../../images/coreFunctionality.png
    :align: center
    :width: 700

.. _project:

Project
-------

These functions will assist in saving, opening and managing GIFtools projects.

    .. toctree::
        :maxdepth: 2
        
        Properties <project/properties>
        Save <project/save>
        Load <project/load>
        Load a recent project <project/loadRecent>
        Add an existing project <project/addProject>
        Viewing options <project/view>              
        Find the version number <project/about>

.. _import:

Import
------

GIFtools is capable of importing data, meshes, physical property models, cells weights, geological maps and other raster-based images, as well as shape files (RGIS vector). For data files, a multitude of data formats are supported, including: GIF format, XYZ format and CSV format. 

    .. toctree::
        :maxdepth: 2

        Import Data <import/data>
        Import Mesh <import/mesh>
        Import Model <import/model>
        Import Weights <import/weights>
        Import Images (Raster) <import/importImage>
        Import Shape Files (RBIS vector) <import/shape>

.. _create:

Create
------

    .. toctree::
        :maxdepth: 2

        Workflow <create/workflow>
        Forward Modeling <create/fwd>
        Inversion <create/inv>
        Model Builder <create/ModelBuilder>
        Equivalent source processing <create/esProcessing>



.. _fwd:

Create >> Inversion
-------------------


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



       
.. _esrc:

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

.. _util:

Fortran utility program
-----------------------

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

.. _utilInterpolateModels:

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

Create >> Survey
----------------

    .. toctree::
        :maxdepth: 1
        
        Create a simple ground or airborne survey <survey/simpleSurvey>


