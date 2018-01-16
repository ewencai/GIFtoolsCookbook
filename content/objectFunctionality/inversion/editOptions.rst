.. _invEditOptions:

.. include:: <isonum.txt>

Edit Options for Inversion Objects
==================================

To set/change the options of the inversion, such as the mesh, data item, topography, or bounds, click on the inversion item, select the menu showing its class (e.g., ``E3Dinversion`` or ``GRAVinversion``):

**[Inversion class]** |rarr| **Edit options**

Edit options are set for the following inversion objects:

	- :ref:`MAG or MAG amplitude inversion<invEditOptions_Mag3D>`
	- :ref:`MVI inversion<invEditOptions_MVI>`
	- :ref:`OCTMAGDE inversion<invEditOptions_MAGOCTDE>`
	- :ref:`GRAV inversion<invEditOptions_Grav3d>`
	- :ref:`EM1DFM sounding<invEditOptions_EM1DFM>`




.. figure:: ../../../images/simpleInvMenu.png
    :align: center
    :width: 400



.. _invEditOptions_Mag3D:

Mag and Mag Amplitude Inversion
-------------------------------

This functionality is responsible for setting all inversion parameters pertaining to the 3D magnetic inversion codes (Mag inversion and Mag amplitude inversion); see `MAG3D background theory <http://mag3d.readthedocs.io/en/latest/content/theory.html>`__. The edit options window is comprised of 3 tabs:

	- **Sensitivity:** Sets the mesh, observed data, topography, `sensitivity weighting <http://mag3d.readthedocs.io/en/latest/content/theory.html#depth-weighting-and-distance-weighting>`__ and `wavelet compression <http://mag3d.readthedocs.io/en/latest/content/theory.html#wavelet-compression-of-sensitivity-matrix>`__
	- **Inversion:** Sets protocols for the :ref:`trade-off parameter<AtoZBeta>` (:math:`\beta`) and all parameters pertaining to the model objective function (:ref:`alphas<AtoZalphas>`, :ref:`cells weights<AtoZWeightingMatrix>`, upper and lower bounds, active cells, reference models and starting models)
	- **Blocky model norms (ver 5.1 and above):** can be activated to recover sparse and blocky models; see :ref:`sparse and blocky norms<AtoZNorms>`

.. figure:: images/grav3d.png
    :align: center
    :width: 700

    Sensitivity (left), inversion (middle) and blocky model norms (right) tabs for MAG inversion and MAG amplitude inversion objects.


.. _invEditOptions_MVI:

MVI Inversion
-------------





.. _invEditOptions_MAGOCTDE:

Mag PDE Inversion
-----------------





.. _invEditOptions_Grav3D:

Grav Inversion
--------------

This functionality is responsible for setting all inversion parameters pertaining to the 3D gravity inversion codes; see `GRAV3D background theory <http://grav3d.readthedocs.io/en/latest/content/theory.html>`__. The edit options window is comprised of 3 tabs:

	- **Sensitivity:** Sets the mesh, observed data, topography, `sensitivity weighting <http://grav3d.readthedocs.io/en/latest/content/theory.html#depth-weighting-and-distance-weighting>`__ and `wavelet compression <http://grav3d.readthedocs.io/en/latest/content/theory.html#wavelet-compression-of-sensitivity-matrix>`__
	- **Inversion:** Sets protocols for the :ref:`trade-off parameter<AtoZBeta>` (:math:`\beta`) and all parameters pertaining to the model objective function (:ref:`alphas<AtoZalphas>`, :ref:`cells weights<AtoZWeightingMatrix>`, upper and lower bounds, active cells, reference models and starting models)
	- **Blocky model norms (ver 5.1 and above):** can be activated to recover sparse and blocky models; see :ref:`sparse and blocky norms<AtoZNorms>`


.. figure:: images/grav3d.png
    :align: center
    :width: 700

    Sensitivity (left), inversion (middle) and blocky model norms (right) tabs for GRAV inversion objects.





.. _invEditOptions_EM1DFM:

EM1DFM Inversion
----------------

This functionality is responsible for setting all inversion parameters pertaining to the EM1DFM code. The list of inversion parameters and their descriptions can be found within the EM1DFM package website; see `main input file <http://em1dfm.readthedocs.io/en/latest/content/files/input_em1dfm.html>`__ and `inversion methodologies <http://em1dfm.readthedocs.io/en/latest/content/theory.html#inversion-methodologies>`__. The edit options window is comprised of 3 tabs:

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













