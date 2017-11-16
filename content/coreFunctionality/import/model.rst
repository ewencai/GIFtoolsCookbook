.. _importModel:

.. include:: <isonum.txt>

Importing a model
=================

.. _importModelCellCentered:

Import a cell centered model
----------------------------

Importing a model first requires a mesh. The import dialog will prompt the user to either choose an existing mesh in the project or browse to load another.

Use the main project menu: **Import** |rarr| **Model** |rarr| **Cell centred**

.. figure:: ../../../images/importModel.png
    :align: center
    :width: 400


**Prerequisites:**

Import a mesh:

- :ref:`1D mesh <importMesh1D>`

- :ref:`2D mesh <importMesh2D>`

- :ref:`3D mesh <importMesh3D>`

- :ref:`OcTree mesh <importMeshOctree>`


**File formats:**

Models can only be imported via :ref:`GIF-formatted <modelfile>` files


.. _importVectorModel:

Import a vector model
---------------------

Importing a model first requires a mesh. The import dialog will have the user either choose a mesh or browse.


Use the main project menu: **Import** |rarr| **Model** |rarr| **Vector**

.. figure:: ../../../images/importModel.png
    :align: center
    :width: 400


**Prerequisites:**

Import a mesh:

- :ref:`2D mesh <importMesh2D>`

- :ref:`3D mesh <importMesh3D>`

- :ref:`OcTree mesh <importMeshOctree>`


**File formats:**

Models can only be imported via :ref:`GIF-formatted vector <modelVectorfile>` files


.. _importActiveModel:

Import an active-cell model
---------------------------

Importing a model first requires a mesh. The import dialog will prompt the user to either choose an existing mesh in the project or browse to load another. **Active cells will contain only values of -1, 0, or 1.**

Use the main project menu: **Import** |rarr| **Model** |rarr| **Active**

.. figure:: ../../../images/importModel.png
    :align: center
    :width: 400


**Prerequisites:**

Import a mesh:

- :ref:`2D mesh <importMesh2D>`

- :ref:`3D mesh <importMesh3D>`

- :ref:`OcTree mesh <importMeshOctree>`


**File formats:**

Active models can only be imported via :ref:`GIF-formatted <modelfile>` files











