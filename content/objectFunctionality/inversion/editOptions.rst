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

	- **Static:** Each transmitter is associated with a distinct sounding. The inversion independently recovers a 1D model for each sounding.
	- **Adaptive:** Here, surface topography is provided. The inversion is carried out in the same way as before, however the vertical locations of models relative to one another are set based on topography
	- **Laterally constrained:** In this approach, the data at each sounding are only sensitive to a particular 1D model. However, the set of 1D models is subject to smoothness constraints in the x and y directions. 


.. figure:: images/em1dfm.png
    :align: center
    :width: 700

    Global (left), conductivity (middle) and susceptibility (right) tabs for EM1DFM inversion objects.


Impact of Topography on Inversion and Plotting in 3D
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Generating the Mesh:**

When survey parameters are set through **FEM sounding** |rarr| **Edit options**, a 3D mesh is generated based on the 1D mesh (layers) provided and the minimum lateral spacing between observation locations. The 3D mesh allows the user to plot the set of recovered 1D models but is not used in any of the inversion approaches. The x and y widths of cells within the 3D mesh are set based on the minimum lateral spacing between observation locations. The top of the 3D mesh corresponds with the elevation of the highest data observation location. The z widths of the cells within the 3D mesh are given directly by the 1D mesh (layers); thus if the 1D mesh has N layers, the 3D mesh will have N cells in the vertical.


.. figure:: images/em1dfm_topo.png
    :align: center
    :width: 700

    Recovered 1D models plotted on a 3D mesh without topography (left) and with (topography).


**Impact on Inversion and Plotting:**

The decision on whether or not to use topography results in two cases. **If topography is not included**, then every layer within the 1D model is active during each independent 1D inversion. Thus if the 1D mesh contains :math:`N` layers, each independently recovered 1D model will have :math:`N` conductivity and/or susceptibility values. When plotted on the 3D mesh at the corresponding horizontal location (based on observation location), all cells in the vertical direction are populated by non-zero values. However, since the top of the 3D mesh corresponds to the elevation of the highest observation location, the tops of all 1D models are also plotted at this height. As a result, data locations will appear underground when 1D models and data are plotted at the same time.

**If topography is included**, then for every independent 1D inversion, the algorithm finds all the layers that would plot below the surface topography on the 3D mesh and sets them as active. Thus if the 1D mesh contained :math:`N` layers, the number of layers that are active in any 1D inversion is :math:`N_{act} \leq N`. When plotting the set of recovered 1D models, the highest non-zero value at each sounding location will correspond to the surface topography and all cells above it will be zero. When creating a 1D mesh, the user must ultimately account for the potential decrease in the number of active cells when deciding to include topography.












