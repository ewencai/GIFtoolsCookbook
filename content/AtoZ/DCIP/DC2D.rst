.. _AtoZDCIP_2DInversion:

2D Inversion
============

.. figure:: ./../../../images/AtoZ_DCIP/AtoZ_DC_inv2D.png
    :align: right
    :figwidth: 50%

In this section, we will invert the :ref:`simulated data <AtoZdcip_Forward>`
in 2D as a pre-processing step for the 3D inversion.

Extract 2D data objects
^^^^^^^^^^^^^^^^^^^^^^^

In the previous :ref:`simulation section <AtoZdcip_Forward>`, we have
generated a ``DC3Ddata`` object, which we first want to invert in 2D:

- :ref:`Assign simple uncertainties <objectAssignUncert>`: floor=:math:`1e-4`
- :ref:`Set the data/uncertainties <objectSetioHeaders>`
- :ref:`Seperate the survey lines <objectdcip3Dto2D_lineID>`
	- Export the 2D topography at 20 m resolution.


Run a Batch Inversion
^^^^^^^^^^^^^^^^^^^^^

We have a total of 10 DC2Ddata objects that would like to invert with similar
parameters. Rather than manually inverting each line, we will make use of the
Batch Inversion object to speedup the process.

- :ref:`Create a DC2Dinversion object <createDCIPInv>` to serve as a template
	- Set :math:`\alpha_s=0.0025, \alpha_x=\alpha_z=1`
- :ref:`Create and edit a Batch Inversion <objectFunctionalityWorkflowBatchInversion>`
- Run all
- Upon completion, load all results

Merge and interpolate models
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

While we can view each inversion result on their respective 2D mesh, in this
section we will bring together the 2D models into our 3D mesh for later use.

- :ref:`Merge results <batchInversionMerge>` using the DCSurveyFull ``lineID`` property as reference

.. figure:: ./../../../images/AtoZ_DCIP/AtoZ_DC_inv2D.png
    :align: center
    :figwidth: 100%

.. note::
		- Resistivity values at depth appear to be higher with the pole-dipole survey. This is consistent with the larger depth penetration of a pole source.
		- Two conductors are more easily identifiable on the East-West (dipole-dipole) survey.
		- The chosen best-fitting halfspace conductivity might be slightly too high due to the thin conductive overburden. The user is invited to repeat the experiment with different background conductivity values.





