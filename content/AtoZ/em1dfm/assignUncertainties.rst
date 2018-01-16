.. _AtoZem1dfm_uncertainties:

.. include:: <isonum.txt>


Specifying Parameters for FEM Sounding Inversion
================================================

Here, we detail the process of defining the survey parameters used in EM1DFM inversions. For `GIF formatted 1D FEM data <http://em1dfm.readthedocs.io/en/latest/content/files/supporting.html>`__, the survey parameters are automatically read into GIFtools. For :ref:`Geosoft XYZ<XYZfile>` and :ref:`CSV<CSVfile>` files however, the survey information must be specified by the user. If not performed correctly, the observation file used in the EM1DFM inversion will not be formatted correctly. In this exercise, we:

    - Define the data columns being imported from a Geosoft XYZ data file
    - Set transmitter, receiver and elevation information
    - Assign uncertainties to the data



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

    - :ref:`Import raw FEM data <importFemData>` (Geosoft XYZ format as an FEM sounding with data in ppm). 
    - :ref:`Import the topography data <importTopo>` (3D GIF format)
    - :ref:`Import 1D mesh<importMesh>` (layers file)


.. tip:: - Use **Edit** |rarr| **Rename** to change what objects in GIFtools are called
         - For any data object, :ref:`edit the data headers <objectDataHeaders>`.
         - Raw data were generated synthetically using the best-available conductivity model for TKC and 3D GIF codes


Add Transmitter, Receiver and Elevation Information
---------------------------------------------------

Since the raw data were loaded in Geosoft XYZ format, we must add the transmitter and receiver information for the airborne survey manually. Additionally, only an altitude column was provided in the raw data. Therefore, we must use the topography and altitude information to determine the elevation of each data point.

    - :ref:`Create elevation from surface topography<objectElevFromSurface>`

        - Click **at surface** and use the altitude data from the FEMsounding object
        - :ref:`Set i/o header<objectSetioHeaders>` for Z to the elevation column you just created

    - :ref:`Add transmitters<objectEMaddTx>` to set the locations of the transmitters **relative to the current xyz data locations**. Use the following parameters:

        - Dipole moment = 1 Am :math:`\! ^2`
        - Set Azimuth angle as "Relative to bearing" and set bearing to calculate
        - Along-line offset = 0 m
        - Cross-line offset = 0 m
        - Set vertical offset as altitude column from data object
        

    - :ref:`Add receivers<objectEMaddRx>` to set the locations of the receivers **relative to the transmitter locations**. Use the following parameters:

        - Dipole moment = 1 Am :math:`\! ^2`
        - Set Azimuth angle as "Relative to bearing" and use the bearing column that was calculate when adding transmitters
        - Along-line offset = 15 m
        - Cross-line offset = 0 m
        - Set vertical offset as altitude column from data object

    - :ref:`Set data normalization to ppm<objectEMsetDataNorm>`


.. figure:: images/dataPlot5000.png
    :align: center
    :width: 700

    Real component of the magnetic field at f = 5000 Hz (left). Imaginary component of the magnetic field at f = 5000 Hz (right)


.. _AtoZem1dfm_uncert_assign:

Assign Uncertainties
--------------------

For this exercise, the set of field observations were created synthetically using the GIF E3D-OcTree code. Noise with a standard deviation of 1 ppm were added to each data point.

    - Use :ref:`assign simple uncertainties<objectAssignUncert>` to assign a floor uncertainty of 1 ppm both the real and imaginary data columns.
    - Set :ref:`i/o headers<objectSetioHeaders>` for all fields



