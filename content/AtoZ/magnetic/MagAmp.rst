.. _AtoZMag_Amp:

Magnetic Amplitude Inversion
============================

Purpose
^^^^^^^

Demonstrate the basic steps for the inversion of magnetic amplitude data.
Amplitude data are weakly sensitive to the orientation of magnetization.
Original work on amplitude inversion comes from our colleagues at `CSM <http://cgem.mines.edu/projects.html>`_ .

.. note:: Link to `MAG3D documentation <http://mag3d.readthedocs.io/en/v6/index.html>`_

Downloads
^^^^^^^^^

.. example::    - `Download the demo <https://github.com/ubcgif/GIFtoolsCookbook/raw/master/assets/AtoZ_mag_4Download.zip>`_
                    - Requires at least `GIFtools version 2.1.3 (Oct 2017) <https://gif.eos.ubc.ca/GIFtools/downloads2#Installation>`_
                    - Requires `MAG3D v6.0 <http://gif.eos.ubc.ca/GIFtools>`_


Step by step
^^^^^^^^^^^^

.. tip:: If you have already completed the :ref:`Magnetic Susceptibility Inversion
		 <AtoZMag_Susc>` demo, you may advance directly to :ref:`Step
		 3<AtoZMagAmp_Step3>`

- **Step 1: Setup**
    - :ref:`Start a GIFtools project <basicFunctionality_index>`
    - :ref:`Set the working directory <projSetWorkDir>`
    - :ref:`Import the topography data <importTopo>`

.. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_Amp.png
    :align: right
    :scale: 30%

    Calculated amplitude data

- **Step 2: Survey and Data**
    - :ref:`Import the magnetic data in UBC format <magfile>`

.. _AtoZMagAmp_Step3:

- **Step 3: Processing**
	- By default, these data are interpreted as TMI data. For GIFtools to recognize as amplitude data, create an magnetic amplitude data object using :ref:`change data type <objectMagDataChangeType>`
	- To create some amplitude data, we will :ref:`forward model data from an existing model <ampStep3>`
	- Once import, remember to :ref:`assign uncertainties <objectAssignUncert>` (1nT) and :ref:`set I/O headers <objectSetioHeaders>`

	- :ref:`Create an inversion object (MAG3D 6.0)<createMagInv>`
	    - :ref:`Edit the options <invEditOptions_Mag3D>`
	        - Panel 1: Fill out Sensitivity Options
	        - Panel 2: Adjust :math:`\alpha` parameters
	        - Click *Apply and write files*

	.. tip:: **Alternatively** if you have already completed the :ref:`Magnetic Susceptibility Inversion <AtoZMag_Susc>` demo, you can :ref:`copy the inversion<invCopyOptions>` object and
		 	 transfer the inversion parameter

.. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_invAmpSmooth.png
            :align: right
            :scale: 20%

- **Step 4: Run the inversion**
    - :ref:`Run all the files <invStep5>`
    - :ref:`Import the inversion results <invStep6>`
    - :ref:`View the convergence curves <invStep7>`

.. note:: The recovered effective susceptibility model shows a near-vertical anomaly, in good agreement with the conceptual idea of a vertical kimberlite pipe.

.. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_InvOptions.png
            :align: right
            :scale: 20%

- **Step 5: Repeat the inversion with sparsity**
    - :ref:`Copy the previous inversion object <invCopyOptions>`
    - Set the sparsity parameters ->
    - :ref:`Import the inversion results <invStep6>`
    - :ref:`View the convergence curves <invStep7>`

.. _AtoZ_Mag_AmpSynthesis:

Synthesis
^^^^^^^^^

- We have recovered a compact effective susceptibility model that honors the amplitude data and resemble the shape of vertical kimberlite pipe.
- Strongest magnetic anomaly is located near and over the zero susceptibility obtained with the :ref:`induced assumption<AtoZ_MagSuscdiscuss>`.

.. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_invAmpCompact.png
            :align: center
            :scale: 75%
