.. _AtoZNS_inversion:

.. include:: <isonum.txt>

.. raw:: html
    :file: ../../../underconstruction.html


Inverting MT Data
=================

Here, we invert synthetic impedance tensor data using E3DMT versions 1 and 2.
The goal is to show both codes are consistent and provide strategies for successful inversion.
When inverting impedances, the E3DMT codes have a tendency to place conductive artifacts proximal to the receivers.
To overcome this obstacle, we demonstrate a basic approach for limiting artifacts through the use of a reference model and interface weights.


.. _AtoZNS_inversion_setup:

Setup for the Exercise
----------------------

**If you have completed the tutorial** :ref:`"Importing, Interpreting and Preparing NSEM Data"<AtoZNS_data>`:

    - Open your preexisting GIFtools project
    - :ref:`Set the working directory <projSetWorkDir>` (if you would like to change it)

**If you have NOT completed the previous tutorial and would like to start here, complete the following steps:**

    - `Download the demo <https://github.com/ubcgif/GIFtoolsCookbook/raw/master/assets/AtoZ_FEM1D_4Download.zip>`_
    - Open GIFtools
    - :ref:`Set the working directory <projSetWorkDir>`
    - :ref:`Import the observed data in E3DMT version 1 format: Assets\\MTdata.obs <importNSEMData_e3dmt1>` (Impedance tensor data in V/A)
    - :ref:`Load OcTree mesh <importMeshOctree>`
    - :ref:`Load active cells model <importActiveModel>`


.. figure:: ../../../images/AtoZ_E3DMT/data_impedance.png
    :align: center
    :width: 700

    Real (left) and imaginary (right) components of impedance tensor element :math:`Z_{xy}` at 5000 Hz in V/A. Data shows that :math:`Z_{xy}` lies in the lower-righthand quadrant of the complext plane. This is consistent with the desired format in GIFtools.


.. figure:: ../../../images/AtoZ_E3DMT/data_appres.png
    :align: center
    :width: 700

    Apparent resistivities for :math:`Z_{xy}` at frequencies 1000 Hz (left), 5000 Hz (middle) and 25000 Hz (right). Apparent resistivity data shows the DO-27 and DO-18 anomalies as conductors. Apparent resistivity data can be created from impedance data using GIFtools.



.. important:: Data were generated using E3DMT version 1 and an interpolation of the best conductivity model for TKC. To keep things simple, the synthetic model was given a constant topography of 425 m. Uncertainties of 0.1 :math:`\pm` 10% were added to all impedance tensor measurements.


Reducing Artifacts through Interface Weighting
----------------------------------------------

When inverting MT data, the E3DMT codes have a tendency to place conductive structures near receiver locations due to the sensitivity of the data to those cells. Here, we generate interface weights to counteract this problem. By forcing lateral smoothness within the top few layers of cells, we can limit the artifacts and force the inversion to place conductive structures at the appropriate depths.



	- :ref:`Create and interface weights utility <createinterfWeights>`
	- Use :ref:`edit options <utilEditOptions>` and set the following parameters:

		- set the OcTree mesh
		- set as *log model*
		- set topography as the active cells model
		- set 5 layers of surface weights with values 40, 20, 10, 5, and 2.5 in decreasing order
		- Face value = 0.0002
		- Face tolerance = 0.0002

	- :ref:`Run the utility <utilRun>`
	- :ref:`Load results <utilLoadResults>`



E3DMT Version 1
---------------

Let us now invert the impedance tensor data using E3DMT version 1. 

	- :ref:`Create E3DMT ver 1 inversion object <createMTZTEMInv>`
	- :ref:`Use edit options <invEditOptions_e3dmt_ver1>` to set the inversion parameters

		- Basic Tab:
			- Select the impedance data
			- Set mesh
			- Set topography to active cells model
			- No background susceptibility
			- 1D conductivity of 0.0001 S/m (which we inferred from apparent resistivity maps)
			- Use *Iterative* solver unless you have sufficient RAM to use *Direct* solver.

		- Model Options Tab:
			- Set *Chi Factor* = 1.
			- *alpha S* = 0.0001, *alpha E* = 1, *alpha N* = 1 and *alpha Z* = 10 (to emphasize some vertical smoothness)
			- Use the weights object to add additional weights
			- Set the *active cells topo* as the active model cells
			- Set initial model as 0.0001 S/m
			- Set upper bound as 1 S/m and lower bound as 0.000001 S/m
			- Set reference model as 0.0001 S/m

	- Click *Apply and write files*
	- :ref:`Run the inversion <invRun>`
	- :ref:`Load results <invLoadResults>`
	- :ref:`View convergence <convergence_curve>`


The results of the inversion are shown below. The convergence curve indicated that the inversion reaches target misfit after 2 iterations. When comparing the true model and recovered model at iteration 2, we see that the inversion recovers the both the DO-27 and DO-18 kimberlite pipes. Surface weighting was able to limit near surface artifacts. However, the recovered model has a slightly lower conductivity than the true model. Given that the starting and reference models are a 0.0001 S/m halfspace, it is possible the uncertainties on the data are too large. When examining the normalized misfit, we see that locations over the pipes are not fit nearly as well as the background. Essentially, we are overfitting the background at the expense of the pipes. Although it is not shown here, we are not over-fitting the data at certain frequencies at the expense of others.


.. figure:: ../../../images/AtoZ_E3DMT/inversion1_convergence.png
    :align: center
    :width: 700

    Convergence curve shows that inversion reaches target misfit.


.. figure:: ../../../images/AtoZ_E3DMT/inversion1.png
    :align: center
    :width: 700

    True model (top) and recovered model at iteration 2 (bottom).


.. figure:: ../../../images/AtoZ_E3DMT/inversion1_misfit.png
    :align: center
    :width: 700

    Normalized misfit for the real component of :math:`Z{xy}` (left) and the imaginary component of :math:`Z{xy}` (right) at 5000 Hz.





E3DMT Version 2
---------------

Let us now invert the impedance tensor data using E3DMT version 2. Unlike version 1, version 2 requires that user define the receiver which measure the fields.

	- Click the impedance data object and :ref:`set receivers from locations <objectDataTypeMT_snid>`. Use the following values:

		- Easting width = 1 m
		- Northing width = 1 m
		- Vertical width = 1 m
		- Dipole length = 1 m

	- :ref:`Create E3DMT ver 2 inversion object <createMTZTEMInv>`
	- :ref:`Use edit options <invEditOptions_e3dmt_ver2>` to set the inversion parameters

		- Basic Tab:
			- Select the impedance data
			- Set mesh
			- Set topography to active cells model
			- No background susceptibility
			- 1D background conductivity of 0.0001 S/m (which we inferred from apparent resistivity maps).
			- Use *Iterative* solver unless you have sufficient RAM to use *Direct* solver.

		- Model Options Tab:
			- Set *Chi Factor* = 1.
			- *alpha S* = 0.0001, *alpha E* = 1, *alpha N* = 1 and *alpha Z* = 10 (to emphasize some vertical smoothness
			- Use the weights object to add additional weights
			- Set the *active cells topo* as the active model cells
			- Set initial model as 0.0001 S/m
			- Set upper bound as 1 S/m and lower bound as 0.000001 S/m
			- Set reference model as 0.0001 S/m

		- Inversion Parameters Tab:
			- Set *memory settings* as *write to file*

	- Click *Apply and write files*
	- :ref:`Run the inversion <invRun>`
	- :ref:`Load results <invLoadResults>`
	- :ref:`View convergence <convergence_curve>`


The final model recovered using E3DMT version 2 is shown below. As we can see, the DO-27 and DO-18 kimerlite pipes are recovered. However when comparing the final recovered models from E3DMT versions 1 and 2, we notice they are slightly different. This can be explained by the following:

	1. The measure of data misfit for both codes is different; see `E3DMT manual <https://e3dmt.readthedocs.io/en/manual_ver1/content/theory.html#data-misfit>`__ . Thus the optimization problem being solved at each beta and the target misfit are both different; which results in recovered models which are not identical.
	2. Because receivers are explicitly defined in E3DMT version 2, there is a difference in how both codes compute predicted data from the solution of the fields on cell edges.

In this case, it is likely that the data uncertainties used to invert data with E3DMT version 2 were too high. The target misfit could be reached using a trade-off parameter (beta) that was larger than necessary and the data are being under-fit. The end result is a model that is overly smooth and has a maximum conductivity which is too low. The user could have run this inversion with a chi factor less than 1 to recover models which put increasing emphasis on fitting the data.


.. figure:: ../../../images/AtoZ_E3DMT/inversion2.png
    :align: center
    :width: 700

    True model (top), final recovered model using E3DMT version 1 and final recovered model using E3DMT version 2 (bottom).
