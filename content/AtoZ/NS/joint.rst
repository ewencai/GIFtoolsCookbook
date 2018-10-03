.. _AtoZNS_joint:

.. include:: <isonum.txt>

.. raw:: html
    :file: ../../../underconstruction.html


ZTEM and Joint Inversion
========================


.. _AtoZNS_inversion_setup:

Setup for the Exercise
----------------------

**If you have completed the tutorial** :ref:`"Importing, Interpreting and Preparing NSEM Data"<AtoZNS_data>`:

    - Open your preexisting GIFtools project
    - :ref:`Set the working directory <projSetWorkDir>` (if you would like to change it)

**If you have NOT completed the previous tutorial and would like to start here, complete the following steps:**

    - `Download the demo <https://github.com/ubcgif/GIFtoolsCookbook/raw/master/assets/AtoZ_FEM1D_4Download.zip>`_
    - Open GIFtools
    - :ref:`Set the working directory <projSetWorkDir>`
    - :ref:`Import the observed MT and ZTEM data in E3DMT version 1 format: Assets\\MTdata.obs <importNSEMData_e3dmt1>` (Impedance tensor data in V/A)
    - :ref:`Load OcTree mesh <importMeshOctree>`
    - :ref:`Load active cells model <importActiveModel>`

.. note:: **SOMETHING ABOUT UNCERTAINTIES**.







E3DMT Version 1
---------------







E3DMT Version 2
---------------

	- :ref:`Set receivers from locations <objectDataTypeMT_snid>`. Use the following values:

		- Easting width = 5 m
		- Northing width = 5 m
		- Vertical width = 5 m
		- Dipole length = 10 m

	- Create an E3DMT version 2 object



