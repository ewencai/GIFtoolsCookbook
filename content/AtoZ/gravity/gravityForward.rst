.. _AtoZGrav_Forward:

.. include:: <isonum.txt>

Forward Model Gravity Data and Compare Against Field Observations
=================================================================

Prelude
-------

Here, we show how GIFtools can be used to forward model gravity data for an arbitrary density model. We consider the case where we have a set of field observations and some a priori knowledge of the local geology; for this example, we know the anomaly is produced by the :ref:`TKC kimberlites <AtoZ_TKCbackground>`. The goal of this exercise is to forward model the survey data for a plausible density model, and see if the predicted gravity anomaly sufficiently matches the anomaly observed in the field data. A reasonable match ensures that our current geological understanding is able to explain the cause of the anomaly.

**NOTE: The same workflow can be used to predict magnetic data for an arbitrary susceptibility or magnetic vector models.**


Download files and start new project
------------------------------------

To complete this exercise, you must first download the necessary files and set up the working directory for your project.

    - Download the demo `Download the demo <https://owncloud.eoas.ubc.ca/s/lDVLwPD2LKI2QKK>`__
    - NOTE: Steps (without links) are also included with the download
    - NOTE: Requires at least GIFtools version 2.1.3 (Oct 2017)
    - :ref:`Set the working directory <projSetWorkDir>`


Import files
------------

In addition to geophysical data, you may have access to topographical information and/or geological surface maps/cross-sections. If this information is available to you, it can be imported to GIFtools. Here, we have surface topography and files which define several geological units through surface mapping.

    - :ref:`Import the topography data <importTopo>` (3D GIF format)
    - :ref:`Import the geology image and link to topography <importImage>` (Image is plane view)
    - :ref:`Create a legend for the geological units in the image <objectGeneralImageCreateLegend>`
    - :ref:`Import field observed gravity anomaly data <importGravData>` (GIF format)

**Note:** observed data were generated synthetically using the best-available density model for TKC.

.. figure:: images/TopoGeologyImage.png
    :align: center
    :figwidth: 100%

    Topography imaged in VTK (left). Plan-view image for surface geological mapping (middle). Gravity anomaly data in gal (right).


Create a Survey
---------------

Ultimately, we would like to predict gravity data for a model of our choosing and compare it against a set of field observations. To accomplish this, we must first create a survey; which has the same properties as the actual survey that was performed. To create the survey, there we have two approaches:

Approach 1: Survey at exact locations
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Using this approach, we will be able to predict gravity data at the EXACT same locations as the field observations. Later on, this will allow us to compute the different between the predicted and observed data. Steps are as follows:

    - Make a :ref:`copy <editcopy>` of the gravity data 
    - Through :ref:`Set I/O headers <objectSetioHeaders>`, remove the I/O header for gravity anomaly data column by setting it to blank
    - :ref:`Delete data column <objectDataDeleteDataColumns>` for pre-existing gravity data (data cannot be deleted if it has an assigned I/O header) 

Approach 2: Custom locations
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    - :ref:`Create simple survey <createSurveySimple>`
        - Set the survey type as 'Gravity'
        - Link the survey to the known topography at TKC
        - Set the height above topography to 10 m
        - Set the following parameters:
            - Easting origin = 556,600
            - Northing origin = 7,133,200
            - Bearing = 0
            - Line length = 1,500
            - Number of survey lines = 15
            - Data spacing = 20
            - Line spacing = 100

**NOTE:** Since the survey parameters are exactly known, approach 1 and approach 2 produce the same thing.

**NOTE:** Both the observed gravity and survey are 'gravity data' objects. Thus they have the same properties and undergo identical actions.

**NOTE:** On the plot below, we see that the colorbar titles are different because the data headers are different. In GIFtools, we can :ref:`edit data headers <objectDataHeaders>`.

.. figure:: images/SurveyCompare.png
    :align: center
    :figwidth: 100%

    Data location from observed data file (left). Data locations for synthetic survey (right).

Create Mesh from Gravity Survey
-------------------------------

To predict field data, we must define the domain by creating a mesh. GIFtools can create meshes based on the data locations and the local topography.

    - :ref:`Create mesh from gravity data <objectDataCreateMesh>`
        - Do not forget to apply topography when creating the mesh!
        - Core cell widths = 25 m
        - Depth of investigation = 400 m
        - Padding = 500 m on each side, 1000 m in depth


.. figure:: images/MeshFromSurvey.png
    :align: center
    :figwidth: 70%

    Mesh created from survey and viewed in VTK. Data locations from the survey have been imported.

**Other ways to make meshes:**

Here, we show one way to create a mesh based on the data locations for your survey. If available, you could also :ref:`import <importMesh>` a pre-existing mesh.

Create Models
-------------

In this step, we design a density model for the geological structure we think will explain the data. We will show that test models can be made quickly using a priori geological information, as opposed to creating a model comprised of uniform blocks. At TKC, we know:

    1. The surface topography
    2. The gravity anomaly is likely caused by the presence of kimberlite pipes
    3. The surface distribution of geological units obtained from geological mapping
    4. The approximate density of kimberlites relative to the host

However, we don't know:

    1. How far down the kimberlites extend
    2. The thickness of any of the kimberlite pipes as a function of depth
    3. The thickness of the overlying till

Create Active Cells Model from Topography
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Regions above the topography have an effective density of 0 and do not contribute towards the gravitational pull experienced at observation locations. For potential field problems, we MUST ensure that data locations lie outside the region of active cells (e.g. within the air cells). Here, we will use the topography data to create an active cells model.

    - :ref:`Creating active cell model from topography <createActiveCellsModel>`
        - Choose 'from tops of cells'


Create Density Model through Model Builder
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Now that we have topography, a mesh, and an active cells model, we can create a density model using all available geological information. To approximate pipe-like structures, we will use the horizontal distributions of each geological unit (obtained from the plan-view image), and project these units down to a desired depth. We will then assign density values to all kimberlite units. Once the geological model has been created, we will output a physical property model which can be used in the forward model. To accomplish this, apply the following steps:

    - :ref:`Start modelBuilder <createModelBuilder>`
    - :ref:`Create geology model from plan-view image <createGeoModelImage>`
        - Use a thickness of 200 m.
    - :ref:`Set physical properties model <propModelFromGeoModel>` for the newly created GEOmodel
        - The approximate difference in density for the kimberlites and till relative to the host is found :ref:`here <AtoZ_TKCbackground>`
    - Set I/O headers to define which information in the geological model is the physical property
    












