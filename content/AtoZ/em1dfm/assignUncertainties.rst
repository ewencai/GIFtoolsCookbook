.. _AtoZem1dfm_uncertainties:

.. include:: <isonum.txt>


Specifying Parameters for FEM Sounding Inversion
================================================

.. figure:: .\..\..\..\images\AtoZ_fem1d\xyz_to_FEM.png
    :align: right
    :scale: 50%

Here, we detail the process of defining the survey parameters used in EM1DFM
inversions. For `GIF formatted 1D FEM data
<http://em1dfm.readthedocs.io/en/latest/content/files/supporting.html>`__, the
survey parameters are automatically read into GIFtools. For :ref:`Geosoft
XYZ<XYZfile>` and :ref:`CSV<CSVfile>` files however, the survey information
must be specified by the user. In this exercise, we:

    - Define the data columns being imported from a Geosoft XYZ data file
    - Set transmitter, receiver and elevation information
    - Assign uncertainties to the data



.. _AtoZem1dfm_setup:

Setup for the Exercise
----------------------

    - `Download the demo <https://github.com/ubcgif/GIFtoolsCookbook/raw/master/assets/AtoZ_FEM1D_4Download.zip>`_
    - Open GIFtools
    - :ref:`Set the working directory <projSetWorkDir>`



.. tip:: - Steps (without links) are also included with the download
         - Requires at least GIFtools version ??? (**! LINK AND VERSION NUMBER NEEDED**)


.. _AtoZem1dfm_import:

Import files
------------

In addition to raw geophysical data, you may have access to topographical information. If this information is available, it can be imported into GIFtools.

    - :ref:`Import raw FEM data <importFemData>` (Geosoft XYZ format as an FEMsounding).
    - :ref:`Import topography data <importTopo>` (3D GIF format)
    - :ref:`Import 1D mesh<importMesh>` (layers file)

.. tip:: - Use **Edit** |rarr| **Rename** to change what objects in GIFtools are called
         - For any data object, :ref:`edit the data headers <objectDataHeaders>`.
         - Raw data were generated synthetically using the best-available conductivity model for TKC and the E3Doctree code


Add Transmitter, Receiver and Elevation Information
---------------------------------------------------

.. figure:: .\..\..\..\images\AtoZ_fem1d\create_FEM_Tx_Rx.png
    :align: right
    :scale: 50%

Since the raw data were formatted according to the Geosoft XYZ format, the transmitter and receiver information for the airborne survey must be set manually. Additionally, only an altitude column was provided in the raw data. Therefore, we must use the topography and altitude information to determine the elevation of each data point.

    - :ref:`Create elevation from surface topography<objectElevFromSurface>`

        - Click **at surface** and use the altitude data column from the FEMsounding object
        - :ref:`Set i/o header<objectSetioHeaders>` for Z to the elevation column you just created

    - :ref:`Add transmitters<objectEMaddTx>` to set the locations of the transmitters **relative to the current xyz data locations**. Use the following parameters:

        - Dipole moment = 1 Am :math:`\! ^2`
        - Set Azimuth angle as "Relative to bearing" and set bearing to calculate
        - Along-line offset = 0 m
        - Cross-line offset = 0 m
        - Set vertical offset as altitude column from data object


    - :ref:`Add receivers<objectEMaddRx>` to set the locations of the receivers **relative to the transmitter locations**. Use the following parameters:

        - Dipole moment = 1 Am :math:`\! ^2`
        - Set Azimuth angle as "Relative to bearing" and use the bearing column that was calculated when adding transmitters
        - Along-line offset = 15 m
        - Cross-line offset = 0 m
        - Set vertical offset as altitude column from data object

    - :ref:`Set data normalization to ppm<objectEMsetDataNorm>`


.. figure:: .\..\..\..\images\AtoZ_fem1d\dataPlot5000.png
    :align: center
    :width: 700

    Real component of the magnetic field at f = 5000 Hz (left). Imaginary component of the magnetic field at f = 5000 Hz (right)


.. _AtoZem1dfm_uncert_assign:

Assign Uncertainties
--------------------

Before inverting the data, we must assign uncertainties. The role of uncertainties in the inversion process is described in the :ref:`inversion fundamentals section<AtoZUncertainties>`. Because real and imaginary components of the observed response span different magnitudes, and the errors on the data may vary as such, distinct floor and percent uncertainties will be computed for each frequency.

    - Use :ref:`assign frequency-dependent uncertainties<objectAssignUncert>` to create data columns containing the data uncertainties. Select "\% of data value" and use the following floor and percent values:

        - :math:`H_{R}` at 1000 Hz = 1 ppm + 10 \%
        - :math:`H_{R}` at 5000 Hz = 2 ppm + 10 \%
        - :math:`H_{R}` at 25000 Hz = 15 ppm + 10 \%
        - :math:`H_{I}` at 1000 Hz = 1 ppm + 2.5 \%
        - :math:`H_{I}` at 5000 Hz = 5 ppm + 2.5 \%
        - :math:`H_{I}` at 25000 Hz = 20 ppm + 2.5 \%

    - Set :ref:`i/o headers<objectSetioHeaders>` for all fields. Files used in the inversion cannot be written until this is performed.

.. note::
    Uncertainties were ascertained experimentally by running a multitude of inversions and examining the final normalized data misfits in each case. If the applied uncertainties are correct:
        - The recovered model does not fit the data too heavily in certain regions at the expense of others
        - The recovered model does not fit the data too heavily at certain frequencies at the expense of others
        - the recovered model fits the real and imaginary components of the data equally

