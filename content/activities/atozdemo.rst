.. _a2zdemo:

.. include:: <isonum.txt>

"A to Z" demo
======================

This demo was created for the Fall 2017 consortium meeting. It is called "A to Z" because it shows how to start from a simple geology image all the way to an inversion, with **everything being done in GIFtools**.

This demo shows how to import a few basic files, design a survey, create a mesh, make a physical property model, forward model data, use that data and invert it.

- **A to Z demo**
	- `Download the demo <https://www.eoas.ubc.ca/~sdevries/ActivitiesForLearning/AtoZ_demo.zip>`__
	- NOTE: Steps (without links) are also included with the download
	- NOTE: Requires at least GIFtools version 2.1.3
- **Steps**
	- Start a new GIFtools project
		- :ref:`Set the working directory <utilSetWorkDir>`
		- :ref:`Import the topography data <importTopo>`
		- :ref:`Import the geology image <importImage>`
		- :ref:`Create a legend for the geology image <legendFile>`
	- :ref:`Create a magnetic survey with the following parameters <surveySimple>`:
		- Height above topography = 50 m
		- Easting origin = 556,440 m
		- Northing origin = 7,133,000 m
		- Bearing = 0 degrees
		- Number of lines = 11
		- Line length = 2000 m
		- Line spacing = 150 m
		- Data spacing = 50 m
	- :ref:`Set the field parameters for the newly created magnetic survey <editFieldParam>`:
		- Inclination = 83.3 degrees
		- Declination = 19.5 degrees
		- Field strength = 59,850 nT
	- :ref:`Create a mesh for the magnetic data <dataCreateMesh>`
		- Core cells = 25 m
		- DOI = 400 m
		- Padding = 500 m on each side, 1000 m in depth
	- Create a model
		- :ref:`Create active cell model on mesh <createActiveCells>`
		- :ref:`Start modelBuilder <createModelBuilder>`
		- :ref:`Create geology model from plan-view image <createGeoModelImage>`. Use a thickness of 200 m. The geology definition is in Notes.txt included with the download
		- :ref:`Create a physical property model <propModelFromGeoModel>`
	- :ref:`Create a forward model <fwdModData>`
		- :ref:`Edit the options <fwdmodStep3>`: set the survey, topography, and model 
		- :ref:`Write the files <fwdModStep4>`
		- :ref:`Run the code <fwdModStep5>`
		- :ref:`Import the predicted data <fwdModStep6>`
	- Work with the predicted data
		- :ref:`View the predicted data <viewData>`
		- :ref:`Add Gaussian noise <addNoise>` (3% and 0 minimum value) and create a new data item
		- :ref:`Assign uncertainties <assignUncert>` using 3% plus a floor of 5 nT
	- :ref:`Create inversion item <invertData>`
		- :ref:`Edit the options <invStep2>`: set the mesh, data, and topography. Everything else can be left as default.
		- :ref:`Write all the files <invStep4>`
		- :ref:`Run all the files <invStep5>`
		- :ref:`Import the inversion results <invStep6>`
		- :ref:`View the convergence curves <invStep7>`






