.. _AtoZem1dfm_uncertainties:

.. include:: <isonum.txt>

.. raw:: html
    :file: ../../../underconstruction.html


Assigning Uncertainties to FEM Data
===================================

Here, we show how GIFtools can be used to ...




.. _AtoZem1dfm_setup:

Setup for the Exercise
----------------------

    - Download the demo (**link**)
    - Open GIFtools
    - :ref:`Set the working directory <projSetWorkDir>`


.. tip:: - Steps (without links) are also included with the download
         - Requires at least GIFtools version ??? (**link**)


.. _AtoZem1dfm_import:

Import files
------------

In addition to raw geophysical data, you may have access to topographical information. If this information is available to you, it can be imported into GIFtools.

    - :ref:`Import raw FEM data <importFemData>` (Geosoft XYZ format as 1D sounding with data in ppm). 
    - :ref:`Import the topography data <importTopo>` (3D GIF format)


.. tip:: - Use **Edit** |rarr| **Rename** to change what objects in GIFtools are called
         - For any data object, :ref:`edit the data headers <objectDataHeaders>`.
         - Raw data were generated synthetically using the best-available conductivity model for TKC and 3D GIF codes


Add Transmitter, Receiver and Elevation Information
---------------------------------------------------

Since the raw data were loaded in Geosoft XYZ format, we must add the transmitter and receiver information for the airborne survey manually. Additionally, only an altitude column was provided in the raw data. Therefore, we must use the topography and altitude information to determine the elevation of each data point.

    - Create elevation from topography
    - :ref:`Add transmitters<objectEMaddTx>` and use the following parameters:
        - Dipole moment = 1 Am :math:`\! ^2`
        - Along-line offset = 15 m
        - Cross-line offset = 0 m
        - Vertical offset = 0 m
        - Normal angle from vertical = 0
        - Azimuthal angle from North = 0

    - :ref:`Add receivers<objectEMaddRx>` and use the following parameters:
        - Dipole moment = 1 Am :math:`\! ^2`
        - Along-line offset = 0 m
        - Cross-line offset = 0 m
        - Vertical offset = 0 m
        - Normal angle from vertical = 0
        - Azimuthal angle from North = 0

    - Convert data from ppm to H/m


