.. _AtoZem1dfm_static:

.. include:: <isonum.txt>


Static 1D Inversion
===================

**Introduction**





.. _AtoZem1dfm_static_setup:

Setup for the Exercise
----------------------

**If you have completed the tutorial** :ref:`"Specifying Parameters for FEM Sounding Inversion"<AtoZem1dfm_uncertainties>`**:**

	- Open your final GIFtools project
	- :ref:`Set the working directory <projSetWorkDir>` (if you would like to change it)

**If you have NOT completed the previous tutorial and would like to start here, complete the following steps:**

    - Download the demo (**link**)
    - Open GIFtools
    - :ref:`Set the working directory <projSetWorkDir>`
    - :ref:`Import raw FEM data <importFemData>` (1D FEM GIF format data in ppm)
    - :ref:`Import the topography data <importTopo>` (3D GIF format)
    - :ref:`Import 1D mesh<importMesh>` (layers file)
    - :ref:`Create elevation from surface topography<objectElevFromSurface>`.
        - Set elevation at 40 m above topography
        - :ref:`Set i/o header<objectSetioHeaders>` for Z to the elevation column you just created.





