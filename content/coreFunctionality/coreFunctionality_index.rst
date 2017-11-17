.. _coreFunctionality_index:

Core/Basic Functionality
========================

The core/basic GIFtools functionality is always accessible through several drop-down menus (:ref:`Project <project>`, Edit, :ref:`Import <import>` and :ref:`Create <create>` ). This functionality allows the user to manage GIF projects, delete/copy/rename objects, import data files and create various GIF objects. Once created, a specific set of actions (or methods) can be carried out on each of these objects. Object-specific methods are described in the :ref:`object-dependent functionality <objectFunctionality_index>` section.

- :ref:`project`: Loading, saving and managing GIF projects
- :ref:`import`: Importing data, mesh, model and other files to GIFtools
- :ref:`create`: Create various GIF objects

.. figure:: ../../images/coreFunctionality.png
    :align: center
    :width: 700

.. _project:

Project
-------

The contents of this drop-down menu will assist in saving, opening and managing GIF projects.

    .. toctree::
        :maxdepth: 1
        
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

GIFtools is capable of importing data, meshes, physical property models, cell weights, geological maps and other raster-based images, as well as shape files (RGIS vector). This information can be imported from a variety of file formats, including: GIF format, XYZ format and CSV format. Once imported, the information/data will be represented in GIFtools as an "object". To see what you can do with each object, visit the :ref:`object-dependent functionality <objectFunctionality_index>` page. The types of information which may be imported to GIFtools is organized as follows:

    .. toctree::
        :maxdepth: 1

        Import Data <import/data>
        Import Mesh <import/mesh>
        Import Model <import/model>
        Import Weights <import/weights>
        Import Images (Raster) <import/importImage>
        Import Shape Files (RBIS vector) <import/shape>

.. _create:

Create
------

Create allows the user to generate objects which are used to carry out a wide variety of tasks. These tasks include: forward modeling various types of geophysical data, inverting geophysical data, interpolating models onto different meshes and performing equivalent source processing for potential fields. By defining the desired task as an object, we can make sure the user only fills in fields and carries out actions which are relevant to the specified task. The actions (or methods) which can be applied to each object are found on the :ref:`object-dependent functionality <objectFunctionality_index>` page. Objects which can be generate through create are as follows:

    .. toctree::
        :maxdepth: 1

        Workflow <create/workflow/workflow_index>
        Forward Modeling <create/fwd/fwd_index>
        Inversion <create/inv/inv_index>
        Processing <create/processing/esProcessing>
        Fortran utility program <create/fortran/fortran_index>
        Create Survey <create/survey/survey_index>
        Model Builder <create/ModelBuilder/ModelBuilder_index>
        









