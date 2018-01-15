.. _objectEMdtype:

.. include:: <isonum.txt>

EM Data Menu
============

.. _objectEMaddTx:

Add Transmitters
----------------

GIF formatted FEM (link) and TEM (link) contain all necessary information pertaining to the transmitters and receivers. However, Geosoft XYZ and CSV formatted FEM and TEM data do not (links). Here, the user may specify the transmitter locations and properties based on the data locations for XYZ and CSV formatted data.

Select the object and the menu **"data type menu"** |rarr| **Add transmitters**


.. figure:: ../../../../images/object/data/em/addTransmitters.png
    :align: center
    :width: 400

    An example of the fields for airborne FEM circular loop transmitters


.. important:: Make sure you have :ref:`set i/o headers<objectSetioHeaders>` for the xyz-data locations. This functionality computes the transmitter locations based on the i/o headers.


FEM or TEM Sounding
^^^^^^^^^^^^^^^^^^^

For FEM and TEM soundings (for use in the 1D codes), the transmitter locations are set **relative to the xyz data locations**. The following parameters are set:

	- **Transmitter:** The dipole moment is set in units :math:`Am^2`
	- **Normal angle from vertical:** Can be defined as a constant value in degrees (0 implies vertical dipole moment) or it can be specified by a data column
	- **Azimuth angle from North:** Clockwise angle in degrees for the dipole moment. Can be set as a constant value or from a data column. Can be set relative to North or relative to the along-line bearing
	- **Bearing:** Bearing sets azimuth angle for the survey in-line direction. If this angle does not exist in a data column, it can be calculate automatically
	- **Along-line offset:** The along-line position of transmitters, relative to the xyz data locations
	- **Cross-line offset:** The cross-line position of transmitters, relative to the xyz data locations
	- **Vertical offset:** The vertical location of the transmitters relative to the surface





.. _objectEMaddRx:

Add Receivers
-------------

GIF formatted FEM (link) and TEM (link) contain all necessary information pertaining to the transmitters and receivers. However, Geosoft XYZ and CSV formatted FEM and TEM data do not (links). Here, the user may specify the receiver locations and properties based on the data locations for XYZ and CSV formatted data.

Select the object and the menu **"data type menu"** |rarr| **Add receivers**

**Requirement:** Transmitters must be set


.. figure:: ../../../../images/object/data/em/addReceivers.png
    :align: center
    :width: 400

    An example of the fields for airborne FEM circular loop receivers


FEM or TEM Sounding
^^^^^^^^^^^^^^^^^^^

For FEM and TEM soundings (for use in the 1D codes), the receiver locations are set **relative to the transmitter locations**. The following parameters are set:

	- **Receiver:** The dipole moment is set in units :math:`Am^2`
	- **Normal angle from vertical:** Can be defined as a constant value in degrees (0 implies vertical dipole moment) or it can be specified by a data column
	- **Azimuth angle from North:** Clockwise angle in degrees for the dipole moment. Can be set as a constant value or from a data column. Can be set relative to North or relative to the along-line bearing
	- **Bearing:** Bearing sets azimuth angle for the survey in-line direction. If this angle does not exist in a data column, it can be calculate automatically
	- **Along-line offset:** The along-line position of receivers, **relative to transmitter locations**
	- **Cross-line offset:** The cross-line position of receivers, **relative to transmitter locations**
	- **Vertical offset:** The vertical location of the receivers relative to the surface









.. _objectEMremoveTx:

Remove Transmitters
-------------------

This functionality allows the user to remove transmitter information from the data object.

Select the object and the menu **"data type menu"** |rarr| **Remove transmitters**