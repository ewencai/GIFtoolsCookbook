.. _fwdEditOptions_dcip:

.. include:: <isonum.txt>

Edit Options for DCIP Forward Modeling Objects
==============================================

.. _fwdEditOptions_dcip2d:

DCIP2D
------

This functionality is responsible for setting all forward modeling parameters pertaining to the "DC2Dforward" and "IP2Dforward" forward modeling codes; see `DCIP2D online manual <http://dcip2d.readthedocs.io/en/latest/index.html>`__ . Within the edit options window, the user may set the following parameters:

    - **Locations:** Observation locations or observed data object. This object contains the electrode locations.

    - **Topography:** Sets topography as

    	- *Default:* Sets topography assuming all electrode are located on the Earth's surface
    	- *Value:* Set the surface to the specified elevation value
    	- *Object:* A 2D topography data object

    - **Conductivity Model:** Set the conductivity model (required for "DC2Dforward" and "IP2Dforward" objects)

    - **Chargeability Model:** Set the chargeability model (not required for "DC2Dforward" objects)

    - **Wave:** To solve the 2D problem, the problem must be solved in the wave domain. *N* specifies the number of log-distribution waves numbers used between *Min* and *Max*. The default is set to: *N* = 13, *Min* = 2.5e-4 and *Max* = 1.

    - **Other options (IP only):** For IP forward modeling, the user may specify if the IP data are computed using a non-linear method or by a linear approximation (in which case the sensitivity is stored)


.. note:: The conductivity and chargeability models are automatically linked to a mesh. That is why a mesh object does not need to be specified within edit options.


.. figure:: ../images/dcip2d.png
    :align: center
    :width: 700


.. _fwdEditOptions_dcip3d:

DCIP3D
------





.. _fwdEditOptions_dcipoctree:

DCIP Octree
-----------









