.. _signConvention:

Coordinates, Sign Conventions and Units: A Quick Guide
======================================================

Here we provide a quick guide for the coordinate systems, time-dependency (:math:`\pm i\omega t`), sign conventions and units used by the GIF Fortran codes and GIFtools GUI. Some important things to note:

- There is some variation in the coordinate systems used to define data locations for various GIF Fortran codes; for example, the EM1DFM code has z +ve down. However when GIF formatted data for any code are loaded into GIFtools, the data locations are transposed from their original coordinate system to X (Easting), Y (Northing) and Z (Elevation). The reverse is also true when exporting GIF formatted data from GIFtools.

|

- In addition to data locations, some GIF Fortran codes have a specific sign convention for the data; for example, the TDoctree code represents the vertical component of the response's time-derivative as :math:`-dB_z/dt`. GIFtools will not change the sign of the data when it is imported/exported. Thus it is important for the user to understand how the data are represented.

|

- If data are loaded using the CSV option, the user is responsible for defining each column. In addition, the user must ensure that the data locations are in the GIFtools coordinate system and that the proper io headers are set.

|




Coordinates for Data Locations
------------------------------

.. tabularcolumns:: |L|C|C|C|C|C|C|

+--------+-----------+-------------+-------+--------+-----+-----+
|  Type  |  Name     |  Versions   |Easting|Northing|Z +ve|LH/RH|
+========+===========+=============+=======+========+=====+=====+
|GUI     |GIFtools   |   N/A       |   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|Gravity |GRAV3D     |5.0, 5.1, 6.0|   Y   |    X   |down | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|Gravity |GRAV PDE   |octree       |   Y   |    X   |down | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|Magnetic|MAG3D      |5.0, 5.1, 6.0|   Y   |    X   |down | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|Magnetic|MAG PDE    |octree       |   Y   |    X   |down | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|MVI     |MVI        |             |   Y   |    X   |down | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|DC/IP   |2D DCIP    |             |   X   |  N/A   |down |N/A  |
+--------+-----------+-------------+-------+--------+-----+-----+
|DC/IP   |3D DCIP    |             |   X   |    Y   |down | LH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|DC/IP   |DCIP octree|octree       |       |        |     |     |
+--------+-----------+-------------+-------+--------+-----+-----+
|FDEM    |EM1DFM     | 1.0         |   X   |   Y    |down | LH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|FDEM    |E3D        |octree       |       |        |     |     |
+--------+-----------+-------------+-------+--------+-----+-----+
|TDEM    |EM1DTM     | 1.0         |   X   |   Y    |down | LH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|TDEM    |H3DTD      |             |       |        |     |     |
+--------+-----------+-------------+-------+--------+-----+-----+
|TDEM    |TDoctree   |octree       |   X   |   Y    | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|MT/ZTEM |MTZ3D      |             |       |        |     |     |
+--------+-----------+-------------+-------+--------+-----+-----+
|MT/ZTEM |E3DMT      |1 (2014,2015)|   X   |   Y    | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|MT/ZTEM |E3DMT      |2 (2017)     |   X   |   Y    | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+





GIF Data Sign Conventions and Time-Dependency
---------------------------------------------

.. tabularcolumns:: |L|C|C|C|

+--------+-----------+-------------+-------------------------------------------------------------+
|  Type  |  Name     |  Versions   |         Sign Convention                                     |
+========+===========+=============+=============================================================+
|Gravity |GRAV3D     |5.0, 5.1, 6.0| +ve data represents +ve gravity anomaly                     |
+--------+-----------+-------------+-------------------------------------------------------------+
|Gravity |GRAV PDE   |octree       | +ve data represents +ve gravity anomaly                     |
+--------+-----------+-------------+-------------------------------------------------------------+
|Magnetic|MAG3D      |5.0, 5.1, 6.0| +ve data represents +ve magnetic anomaly                    |
+--------+-----------+-------------+-------------------------------------------------------------+
|Magnetic|MAG PDE    |octree       | +ve data represents +ve magnetic anomaly                    |
+--------+-----------+-------------+-------------------------------------------------------------+
|MVI     |MVI        |             | +ve data represents +ve magnetic anomaly                    |
+--------+-----------+-------------+-------------------------------------------------------------+
|DC/IP   |2D DCIP    |             |:math:`\mathbf{E}=-\nabla V` and :math:`\Delta V = V_N - V_M`|
+--------+-----------+-------------+-------------------------------------------------------------+
|DC/IP   |3D DCIP    |             |:math:`\mathbf{E}=-\nabla V` and :math:`\Delta V = V_N - V_M`|
+--------+-----------+-------------+-------------------------------------------------------------+
|DC/IP   |DCIP octree|octree       |:math:`\mathbf{E}=-\nabla V` and :math:`\Delta V = V_N - V_M`|
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Time-dependency is :math:`+i\omega t`                     |
|FDEM    |EM1DFM     | 1.0         | - Hx, Hy, Hz                                                |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             |                                                             |
|FDEM    |E3D        |octree       |                                                             |
|        |           |             |                                                             |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Hx, Hy, Hz                                                |
|TDEM    |EM1DTM     |1.0          | - dBx/dt, dBy/dt, dBz/dt                                    |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             |                                                             |
|TDEM    |H3DTD      |             |                                                             |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Hx, Hy, Hz                                                |
|TDEM    |TDoctree   |octree       | - dBx/dt, dBy/dt, -dBz/dt                                   |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             |                                                             |
|MT/ZTEM |MTZ3D      |             |                                                             |
|        |           |             |                                                             |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Time-dependency is                                        |
|MT/ZTEM |E3DMT      |octree ver. 1|                                                             |
|        |           |             |                                                             |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Time-dependency can be chosen as :math:`\pm i\omega t`    |
|MT/ZTEM |E3DMT      |octree ver. 2|                                                             |
|        |           |             |                                                             |
+--------+-----------+-------------+-------------------------------------------------------------+


**Gravity and Magnetics:**



**DCIP data:**

In the electrostatic case, the Ampere-Maxwell equation shows that :math:`\nabla \times \mathbf{E} = 0` and that :math:`\mathbf{E}` can be written as the gradient of a scalar potential:

.. math::
	\mathbf{E} = \pm \nabla V.

By taking the divergence of Faraday`s law and substituting the previous expression, the DC resistivity problem is ultimately defined by the following expression:

.. math::

	- \nabla \cdot \sigma (\pm \nabla V) = \nabla \cdot \mathbf{j_e}.

As we can see, our choice in the relationship between :math:`\mathbf{E}` and :math:`V` changes the sign convention for the voltage measurements. In the case of UBC GIF codes, we choose :math:`\mathbf{E} = - \nabla V`.


**H3DTD and TDoctree data:**

For a coincident loop airborne system, the transient voltage induced in the receiver coil is positive and decaying. According to Faraday's law, the voltage induced in the receiver coil is proportional to :math:`-dBz/dt`; thus the true :math:`dBz/dt` response is negative and decays as a function of time. The sign convention used by these codes maintains the correct sign for :math:`dBx/dt` and :math:`dBy/dt`. However, it uses :math:`-dBz/dt` so that the vertical transient response is plotted as a positive decaying function for most airborne systems. 


Units
-----

**Physical Property Definitions:**

	- :math:`\boldsymbol{\rho :}` density
	- :math:`\boldsymbol{\kappa :}` susceptibility or effective susceptibility
	- :math:`\boldsymbol{\sigma :}` conductivity
	- :math:`\boldsymbol{\eta :}` Intrinsic chargeability. If linear option chosen, any convention of intrinsic or integrated chargeability is acceptible.

**Data Type Definitions:**

	- :math:`\Delta V:` Potential different (voltage)
	- :math:`\mathbf{H}:` Magnetic field intensity (auxiliary field) 
	- :math:`\mathbf{B}:` Magnetic flux density
	- :math:`\partial \mathbf{B}/\partial t:` Time-derivative of the magnetic flux density
	- :math:`Z_{ij}:` The ij-th element of the impedance tensor
	- :math:`T_i:` The x or y component of the ZTEM transfer function


.. tabularcolumns:: |L|C|C|C|C|

+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|  Type  |  Name     |  Versions   |     Property Units                    | Data Units                               |
+========+===========+=============+=======================================+==========================================+
|Gravity |GRAV3D     |5.0, 5.1, 6.0|:math:`\rho = g/cm^3`                  | mGal                                     |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|Gravity |GRAV PDE   |octree       |:math:`\rho = g/cm^3`                  | mGal                                     |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|Magnetic|MAG3D      |5.0, 5.1, 6.0|:math:`\kappa = SI`                    | nT                                       |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|Magnetic|MAG PDE    |octree       |:math:`\kappa = SI`                    | nT                                       |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|MVI     |MVI        |             |:math:`\kappa = SI`                    | nT                                       |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 |Observed voltage normalized by the        |
|DC/IP   |2D DCIP    |             |- :math:`\eta \in [0,1]`               |transmitter current (:math:`\Delta V /I`) |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 |Observed voltage normalized by the        |
|DC/IP   |3D DCIP    |             |- :math:`\eta \in [0,1]`               |transmitter current (:math:`\Delta V /I`) |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|        |           |octree       |- :math:`\sigma = S/m`                 |Observed voltage normalized by the        |
|DC/IP   |DCIP octree|             |- :math:`\eta \in [0,1]`               |transmitter current (:math:`\Delta V /I`) |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 |                                          |
|FDEM    |EM1DFM     | 1.0         |- :math:`\kappa = SI`                  |                                          |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 |                                          |
|FDEM    |E3D        |octree       |- :math:`\kappa = SI` (background only)|                                          |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|TDEM    |EM1DTM     |1.0          |:math:`\sigma = S/m`                   |                                          |
|        |           |             |                                       |                                          |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|        |           |             |                                       |                                          |
|TDEM    |H3DTD      |             |                                       |                                          |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 |                                          |
|TDEM    |TDoctree   |octree       |- :math:`\kappa = SI` (background only)|                                          |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 |- :math:`Z_{ij}:` V/A                     |
|MT/ZTEM |MTZ3D      |             |- :math:`\kappa = SI` (background only)|- :math:`T_i:` unitless                   |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 |- :math:`Z_{ij}:` V/A                     |
|MT/ZTEM |E3DMT      |octree ver. 1|- :math:`\kappa = SI` (background only)|- :math:`T_i:` unitless                   |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 |- :math:`Z_{ij}:` V/A                     |
|MT/ZTEM |E3DMT      |octree ver. 2|- :math:`\kappa = SI` (background only)|- :math:`T_i:` unitless                   |
+--------+-----------+-------------+---------------------------------------+------------------------------------------+