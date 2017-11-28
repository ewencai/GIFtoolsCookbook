.. _AtoZGrav_Corrections:

.. include:: <isonum.txt>

Data Corrections for Gravity Data
=================================

Prelude
-------

ADD PRELUDE

.. _AtoZGrav_Forward_Download:

Download files and start new project
------------------------------------

To complete this exercise, you must first download the necessary files and set up the working directory for your project.

.. example:: - `Download the demo <https://owncloud.eoas.ubc.ca/s/lDVLwPD2LKI2QKK>`__
             - :ref:`Set the working directory <projSetWorkDir>`

.. tip:: - Steps (without links) are also included with the download
         - Requires at least GIFtools version 2.1.3 (Oct 2017)


.. _AtoZGrav_Corrections_Import:

Import files
------------

In addition to raw geophysical data, you may have access to topographical information and/or geological surface maps/cross-sections. If this information is available to you, it can be imported to GIFtools. Here, we have surface topography and files which define several geological units through surface mapping.

    - :ref:`Import the topography data <importTopo>` (3D GIF format)
    - :ref:`Import raw gravity data <importGravData>` (GIF format with data in mGal)

.. tip:: - Use **Edit** |rarr| **Rename** to change what objects in GIFtools are called
         - For any data object, :ref:`edit the data headers <objectDataHeaders>`. We set the observed gravity data to "Gravity (mGal)"
         - Observed data were generated synthetically using the best-available density model for TKC.

Latitude and Free-Air Correction
--------------------------------

Here, we show how GIFtools can used to carry out latitude and free-air corrections on raw gravity data. This correction accounts for all of the mass contained within the reference ellipsoid approximation of the Earth. Although it may be necessary to apply distinct latitude corrections for each survey location, here we will apply only a constant correction; wherein we assume all survey location are at a latitude of 64 :math:`\! ^o` N. Because the elevation of the survey varies with topography, the free-air correction which must be applied to each datum is different. The following expressions can be use to compute the latitude and free-air corrections:


**Latitude Correction:**

.. math::
	\begin{align}
	\Delta g_l &= 978,031.8 \times \big [ 1 + 0.0053024 \, sin^2 \phi - 0.0000059 \, sin^2 (2\phi) \big ] \\
	&= 982217.559014 \textrm{ mGal at TKC}
	\end{align}


**Free Air Correction:**

.. math::
	\Delta g_{fa} = 0.3086 \times Elevation(m) \;\; (in \; mGal)

To apply these corrections to the raw data, carry out the following steps:

	- With the latitude correction provided, use the :ref:`constant calculator <objectConstantCalculator>` to remove this value from the raw data and create a new column. **Carry all decimal places!**
	- Using the :ref:`constant calculator <objectConstantCalculator>`, compute the free-air correction that must be added to each survey location.
	- Using the :ref:`column calculator <objectColumnCalculator>`, apply the free-air correction.

.. tip:: To keep track of data columns, remember to :ref:`edit data headers <objectDataHeaders>`.



Topography and Regional Geology Correction
------------------------------------------

If the topography is flat, you may choose to use a Bouguer correction; which accounts for the mass which lies between the reference ellipsoid and your survey elevation. Here, we show how the background density and surface topography can be use to remove the gravity contribution from the background geology.


Create a Mesh
^^^^^^^^^^^^^

    - :ref:`Create a mesh using gravity data <objectDataCreateMesh>` with the following parameters:
        - Don't forget to apply topography when creating the mesh!
        - Core cell widths = 25 m
        - Extent above = 0 m
        - Depth of investigation = 425 m
        - Padding = 2000 m on each side, 0 m in depth
        - Padding factor = 1.2

Create Active Cells from Topography
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

	- :ref:`Create active cells model from topography <createActiveCellsModel>`
        - Choose 'from tops of cells'

Create a Constant Density Model
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^





