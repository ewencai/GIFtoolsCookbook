.. _AtoZDCIP_simulation:


Survey Design and Forward Simulation
====================================

.. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_Landing.png
    :align: right
    :figwidth: 50%

Here, we show how to create a simple dipole-dipole DC Resistivity survey over
a conductivity model.



.. _AtoZdcip_setup:

Setup for the Exercise
----------------------

    - `Download the demo <https://github.com/ubcgif/GIFtoolsCookbook/raw/master/assets/AtoZ_DCIP_4Download.zip>`_
    - Open GIFtools
    - :ref:`Set the working directory <projSetWorkDir>`


.. tip:: - Steps (without links) are also included with the download
         - Requires at least `GIFtools version 2.26 <https://gif.eos.ubc.ca/giftools/giftools_consortium2#Installation>`_ (login required)


- Create surveys

+-------------------+-----------------------+-----------------------+
|                   | Block 1               | Block 2               |
+-------------------+-----------------------+-----------------------+
| Survey Type       |   pole-dipole         | dipole-dipole         |
+-------------------+-----------------------+-----------------------+
| Centroid          | 557250 E, 7134000 N   | 557400 E, 7133600 N   |
+-------------------+-----------------------+-----------------------+
| Bearing           | 45d                   | 90d                   |
+-------------------+-----------------------+-----------------------+
| Line Length       | 1500                  | 1500                  |
+-------------------+-----------------------+-----------------------+
| Line Spacing      | 300                   | 100                   |
+-------------------+-----------------------+-----------------------+
| Nb. lines         | 5                     | 5                     |
+-------------------+-----------------------+-----------------------+
| Electrode Spacing | 60                    | 60                    |
+-------------------+-----------------------+-----------------------+
| Nb. Receivers     | 20                    | 20                    |
+-------------------+-----------------------+-----------------------+


- Merge surveys
- Apply topography
- Run DCIP3D forward
- Add noise
- View data


