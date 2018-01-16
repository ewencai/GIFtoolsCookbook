.. _invEditOptions:

.. include:: <isonum.txt>

Edit the inversion's options
============================

To change the options of the inversion, such as the mesh, data item, topography, or bounds, click on the inversion item, select the menu showing its class (e.g., ``E3Dinversion`` or ``GRAVinversion``):

**[Inversion class]** |rarr| **Edit options**

Inversion objects include:

	- :ref:`EM1DFM<invEditOptions_EM1DFM>`




.. figure:: ../../../images/simpleInvMenu.png
    :align: center
    :width: 400



















.. _invEditOptions_EM1DFM:

EM1DFM Inversion
----------------

This functionality is responsible for setting all inversion parameters pertaining to the EM1DFM code. The list of inversion parameters and their descriptions can be found here (**see EM1DFM manual**). The edit options window is comprised of 3 tabs:

	- **Global:** Sets global inversion parameters such as the 1D mesh, data object, 1D inversion type, model type and computation of the trade-off parameter
	- **Conductivity:** specifies the starting model, reference model and regularization for conductivity in the inversion
	- **Susceptibility:** specifies the starting model, reference model and regularization for susceptibility in the inversion

GIFtools is capable of carrying out three distinct 1D inversion approaches:

	- **Static:** Each transmitter is associated with a distinct sounding. The inversion independently recovers a 1D model for each sounding. Inversion results are plotted on a pseudo-3D mesh.
	- **Adaptive:** Here, surface topography is provided. The inversion is carried out in the same way as before, however the vertical locations of models relative to one another are set based on topography
	- **Laterally constrained:** In this approach, the data at each sounding are only sensitive to a particular 1D model. However, the set of 1D models is subject to smoothness constraints in the x and y directions. 


.. figure:: images/em1dfm.png
    :align: center
    :width: 700

    Global (left), conductivity (middle) and susceptibility (right) tabs for EM1DFM inversion objects.













