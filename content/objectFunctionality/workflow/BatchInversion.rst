.. _objectFunctionalityWorkflowBatchInversion:

.. include:: <isonum.txt>

Batch Inversion
===============

.. figure:: ../../../images/Workflows/batchInversion_Folder.png
    :align: right
    :figwidth: 40%

With a ``BatchInversion`` object, the user can schedule to run several
independent inversions (data, topography, mesh) but with common inversion
parameters. This ``Workflow`` was primarily designed to reduce the processing
time of DCIP2D data. Inversion objects are created and stored under
a common folder structure. Recovered models can be merged for viewing in 3D.


.. _batchInversionCreate:

Create Batch Inversion
^^^^^^^^^^^^^^^^^^^^^^

.. figure:: ../../../images/createWorkflowBatchInversionMenu.png
    :align: center
    :figwidth: 40%

``Batch Inversion`` object can be created through the ``Project`` menu structure:

**Create** |rarr| **Workflow** |rarr| **Batch Inversion**

.. _batchInversionMerge:

Merge Results
^^^^^^^^^^^^^







