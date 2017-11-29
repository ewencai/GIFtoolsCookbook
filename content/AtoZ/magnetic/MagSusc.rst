.. _AtoZMag_Susc:

.. include:: <isonum.txt>

Magnetic Susceptibility:
========================

Purpose
^^^^^^^

Demonstrate the basic steps for the inversion of magnetic data using the
induced magnetization assumption. We will start directly with *simulated* data
and topography, as it is often the case in a greenfield exploration project.

.. note:: Link to `MAG3D documentation <http://mag3d.readthedocs.io/en/v6/index.html>`_

Downloads
^^^^^^^^^

.. example::    - `Download the demo <https://github.com/ubcgif/GIFtoolsCookbook/raw/master/assets/AtoZ_mag_4Download.zip>`__
                    - Requires at least `GIFtools version 2.1.3 (Oct 2017) <https://gif.eos.ubc.ca/GIFtools/downloads2#Installation>`_
                    - Requires `MAG3D v6.0 <http://gif.eos.ubc.ca/GIFtools>`_


Step by step
^^^^^^^^^^^^

- **Step 1: Setup**
    - :ref:`Start a GIFtools project <basicFunctionality_index>`
    - :ref:`Set the working directory <projSetWorkDir>`
    - :ref:`Import the topography data <importTopo>`

.. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_LoadXYZ.png
    :align: right
    :scale: 30%

    *Click on image*

- **Step 2: Survey and Data**
    - :ref:`Import magnetic data in XYZ format <importMagData>`

    .. tip:: Assign the Easting and Northing (X, Y), but leave elevation empty. Make sure you load in both the *ralt* and *B_igrf* variables

    - :ref:`Set the field parameters for the newly created magnetic survey <objectEditFieldParam>`:
        - Field strength = 59,850 nT
        - Inclination = 83.3 degrees
        - Declination = 19.5 degrees

    .. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_SyntheticData_trended.png
        :align: right
        :scale: 20%

    - :ref:`Remove the IGRF from the tmi data<objectRemoveIGRF>`
    - :ref:`Assign Z value from radar altimeter and topography<assignElevTopo>`
    - :ref:`Set data uncertainties (1nT floor) <objectAssignUncert>`

    .. note:: - The observed magnetic data is now ready for export.
              - At least two anomalies are easily identified.
              - Note the large trend in the data coming from the NE.

.. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_MeshParam.png
    :align: right
    :scale: 15%

    *Mesh specs*

.. _AtoZMag_invObj:

- **Step 3: Processing**
    - :ref:`Create a mesh from the observed data <objectDataCreateMesh>`
        - To reproduce this example, use the following parameters
    - :ref:`Create an inversion object (MAG3D 6.0)<createMagInv>`

    .. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_InvOptions.png
        :align: right
        :scale: 15%

        Inversion parameters

    .. _AtoZMag_alphaOpt:

    - :ref:`Edit the options <invEditOptions>`
        - Panel 1: Fill out Sensitivity Options
        - Panel 2: Adjust :math:`\alpha` parameters
        - Click *Apply and write files*

.. tip:: As a general *best practice*, in the absence of a priori
         information, :math:`\alpha` values should be set such that all components of
         the regularization have equal weight. Based on the core mesh discretization:
         :math:`\alpha_s = \left[\frac{1}{dx}\right]^2` and :math:`\alpha_z = \left[\frac{1}{2}\right]^2`.

.. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_invTrend.png
            :align: right
            :scale: 20%

- **Step 4: Run the inversion**
    - :ref:`Run all the files <invStep5>`
    - :ref:`Import the inversion results <invStep6>`
    - :ref:`View the convergence curves <invStep7>`

.. note:: Note the linear anomalies recovered on the edges of the core
          mesh. This feature is due to the regional signal captured by our survey, but extents beyond the region of interest.
          We can improve our result with the following step.

.. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_SyntheticData.png
            :align: right
            :scale: 20%

            De-trended data

- **Step 5: De-trend and re-run**
    - :ref:`Remove first-order trend<objectPolyTrend>`

    - :ref:`Create a new inversion copy <invCopyOptions>`
    - **Repeat Step 4**

 .. note:: Note the large negative lobe along the NE edge of the southern mag anomaly.

.. _AtoZ_MagSuscdiscuss:

Synthesis
^^^^^^^^^

.. figure:: ./../../../images/AtoZ_Mag/AtoZ_Mag_Misfit.png
        :align: right
        :scale: 30%

        Data residual

- We have recovered a susceptibility model that honors the data within the target misfit.
- Considering a near-vertical inducing field, at least two features should raise some serious flags regarding the presence of remanence.
    - The kimberlite pipe appears to be plunging towards SW, with a cone-shape zone of zero susceptibility.
    - The data residual map shows correlated signal near the main anomaly, indicative of poor fit of the large negative anomaly

.. figure:: ./../../../images/AtoZ_Mag/AtoZ_MagSusc.png
        :align: center
        :scale: 75%

        Recovered susceptibility model



