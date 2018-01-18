.. _AtoZem1dfm_static:

.. include:: <isonum.txt>


Static and Adaptive 1D Inversion
================================

Here, FEM data are inverted using both static and adaptive 1D inversion approaches. The adaptive approach takes into account surface topography whereas the static approach does not. In either case, every transmitter is associated with a distinct sounding location. A 1D model is then recovered independently for each sounding location; see the `EM1DFM package overview <http://em1dfm.readthedocs.io/en/latest/content/overview.html>`__ for background theory. The set of recovered 1D models are interpolated and visualized on a 3D mesh. Static and adaptive 1D inversion algorithms are a computationally fast way to obtain depth and horizontal location information about conductive/resistive and magnetically susceptible targets.

As part of this exercise, the user will:

    - Create EM1DFM inversion objects
    - Set relevant inversion parameters
    - Attempt to explain the set of field observations using a set of 1D conductivity models (susceptibility models can be included)
    - Examine inversion results which incorporate surface topography (adaptive approach)
    - Interpret inversion results generated from 1D inversions

.. _AtoZem1dfm_static_setup:

Setup for the Exercise
----------------------

**If you have completed the tutorial** :ref:`"Specifying Parameters for FEM Sounding Inversion"<AtoZem1dfm_uncertainties>`:

    - Open your preexisting GIFtools project
    - :ref:`Set the working directory <projSetWorkDir>` (if you would like to change it)

**If you have NOT completed the previous tutorial and would like to start here, complete the following steps:**

    - Download the demo (**link**)
    - Open GIFtools
    - :ref:`Set the working directory <projSetWorkDir>`
    - :ref:`Import raw FEM data <importFemData>` (1D FEM GIF format data in ppm)
    - :ref:`Import the topography data <importTopo>` (3D GIF format)
    - :ref:`Import 1D mesh<importMesh>` (layers file)
    - :ref:`Create elevation from surface topography<objectElevFromSurface>`
        - Set elevation at 40 m above topography
        - :ref:`Set i/o header<objectSetioHeaders>` for Z to the elevation column you just created.


.. figure:: images/dataPlot5000.png
    :align: center
    :width: 700

    Real component of the magnetic field at f = 5000 Hz (left). Imaginary component of the magnetic field at f = 5000 Hz (right)


Static 1D FEM Inversion
-----------------------

Here, the set of FEM data are inverted using the static 1D approach.

Setup the inversion
^^^^^^^^^^^^^^^^^^^

    - :ref:`Create an EM1DFM inversion object <createFEMInv>` and set the output directory
    - Set the EM1DFM inversion parameters under :ref:`edit options<invEditOptions>`:
        - **Global tab**:
            - **Set mesh from drop-down menu**
            - **Set observed data from drop-down menu**
            - **Mode:** static 1D
            - **Model options:** for this example, data are inverted strictly for a conductivity model
            - **Solver options:** leave as default or customize
            - **Trade-off Mode:** leave as default or customize
        - **Conductivity tab:**
            - Leave as default or customize
        - **Susceptibility tab:**
            - Leave as default or customize (if being used)
        - Click apply and write all files


.. note:: If you chose not to write the files from the edit options menu, you may do so through :ref:`write inversion files <invWriteAll>`


Run Inversion and Load Results
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    - :ref:`Run inversion <invRun>`
    - :ref:`Load results <invLoadResults>`
    - :reF:`View the results <viewData>`

Discussion
^^^^^^^^^^

**Image of inversion results and misfit**


Adaptive 1D FEM Inversion
-------------------------

Here, the set of FEM data are inverted using the adaptive 1D approach. In this case, surface topography is used to position the vertical locations of recovered 1D models relative to one another; i.e. the surface of each 1D model should correspond with the surface location.


Setup the inversion
^^^^^^^^^^^^^^^^^^^

    - Create another EM1DFM inversion using :ref:`copy options<invCopyOptions>`
    - Click on the newly created EM1DFM inversion object and set the output directory
    - Use :ref:`edit options<invEditOptions>` to verify and apply the current set of inversion parameters:
        - Make sure the mesh and observed data are properly set
        - Set the topography from the drop-down menu
        - Notice that the inversion parameters are identical to the previous inversion that was run
        - Apply and write all files


Run Inversion and Load Results
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    - :ref:`Write inversion files <invWriteAll>`
    - :ref:`Run inversion <invRun>` (select desired input file)
    - :ref:`Load results <invLoadResults>`
    - :reF:`View the results <viewData>`

Discussion
^^^^^^^^^^

**Image of inversion results and misfit**






