.. _downsample:

.. include:: <isonum.txt>

Downsample data
===============

Data may be downsample in two ways: traditional removal and a mesh-based removal. With any method that deletes data locations, a *new* data object will be created after downsampling. See below for details.

Traditional downsampling
^^^^^^^^^^^^^^^^^^^^^^^^

Traditional downsampling requires a number, :math:`n`, which represents the fractional number of data kept (e.g, 3 is one-third, 4 is one-quarter). This downsampling can be done on any data object as the algorithm finds only the unique *horizontal* locations of data. To downsample the data this way, the menu structure is:

**Data manipulation** |rarr| **Downsampling** |rarr| **Simple**

.. figure:: ../../../images/downsample.png
    :align: center
    :width: 400


**NOTE:** This method of downsampling can be reached from the :ref:`data viewer <viewData>`. Data first need to be selected (to either be downsampled or left alone) via the **View** |rarr| **Edit** |rarr| **Data selection** tab of the viwer control dialog. Then select its neighbouring tab: **View** |rarr| **Edit** |rarr| **Simple edit** and select the radio button under "Downsample area." The value associated with this will be :math:`n` as given above. A new data object name will be required.


.. figure:: ../../../images/downsampleFromViewer.png
    :align: center
    :width: 400


Downsample by mesh
^^^^^^^^^^^^^^^^^^
The second method of downsample requires a mesh (either :ref:`3D<importMesh3D>` or :ref:`ocTree<importMeshOctree>`) and will keep only one datum location per cell. EM data will have its times/frequencies preserved. The option also allows for either the closest location to the centre of each cell or a random location in each cell will be chosen. To access this function use:

**Data manipulation** |rarr| **Downsampling** |rarr| **Mesh Based**

.. figure:: ../../../images/downsample.png
    :align: center
    :width: 400
 

