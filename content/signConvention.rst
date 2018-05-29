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

Here, we define the coordinate systems for data points for each code. In general X is Easting, Y is Northing and Z is +ve up. However the 1D codes are an exception; where -ve Z locations refer to positions above ground and the coordinate system is left-handed. Certain codes may use a different coordinate system internally. However, the majority of users will not need to worry about this.


.. tabularcolumns:: |L|C|C|C|C|C|C|

+--------+-----------+-------------+-------+--------+-----+-----+
|  Type  |  Name     |  Versions   |Easting|Northing|Z +ve|LH/RH|
+========+===========+=============+=======+========+=====+=====+
|GUI     |GIFtools   |   N/A       |   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|Gravity |GRAV3D     |5.0, 5.1, 6.0|   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|Gravity |GRAV PDE   |octree       |   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|Magnetic|MAG3D      |5.0, 5.1, 6.0|   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|Magnetic|MAG PDE    |octree       |   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|MVI     |MVI        |             |   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|DC/IP   |DCIP2D     |  3.1, 5.0   |   X   |  N/A   | up  | N/A |
+--------+-----------+-------------+-------+--------+-----+-----+
|DC/IP   |DCIP3D     |             |   X   |    Y   | up  | LH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|DC/IP   |DCIPoctree |octree       |   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|FDEM    |EM1DFM     | 1.0         |   X   |    Y   |down | LH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|FDEM    |EH3D       |             |   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|FDEM    |E3D        |octree       |   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|TDEM    |EM1DTM     | 1.0         |   X   |   Y    |down | LH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|TDEM    |H3DTD      |             |   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|TDEM    |TDoctree   |octree       |   X   |   Y    | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|MT/ZTEM |MTZ3D      |             |   X   |    Y   | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|MT/ZTEM |E3DMT      |1 (2014,2015)|   X   |   Y    | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+
|MT/ZTEM |E3DMT      |2 (2017)     |   X   |   Y    | up  | RH  |
+--------+-----------+-------------+-------+--------+-----+-----+

.. note::
	- Potential fields should be pretty straight forward
	- Example data files for DCIP2D, DCIP3D and DCIPoctree show borehole data as having -ve Z locations. Thus we believe it is right-handed with Z +ve up. **However**, the z location may be defined as a distance relative to the top of the mesh.
	- There is no indication that any CSEM codes (other than 1D codes) are in a coordinate system other than X (easting), Y (northing) and Z (+ve up). Example data files in manuals put Z locations as positive numbers.



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

+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|  Type  |  Name     |  Versions   |     Property Units                    | Data Units                                       |
+========+===========+=============+=======================================+==================================================+
|Gravity |GRAV3D     |5.0, 5.1, 6.0|:math:`\rho = g/cm^3`                  | mGal                                             |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|Gravity |GRAV PDE   |octree       |:math:`\rho = g/cm^3`                  | mGal                                             |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|Magnetic|MAG3D      |5.0, 5.1, 6.0|:math:`\kappa = SI`                    | nT                                               |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|Magnetic|MAG PDE    |octree       |:math:`\kappa = SI`                    | nT                                               |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|MVI     |MVI        |             |:math:`\kappa = SI`                    | nT                                               |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 |Observed voltage normalized by the                |
|DC/IP   |2D DCIP    |             |- :math:`\eta \in [0,1]`               |transmitter current (:math:`\Delta V /I`)         |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 |Observed voltage normalized by the                |
|DC/IP   |3D DCIP    |             |- :math:`\eta \in [0,1]`               |transmitter current (:math:`\Delta V /I`)         |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|        |           |octree       |- :math:`\sigma = S/m`                 |Observed voltage normalized by the                |
|DC/IP   |DCIP octree|             |- :math:`\eta \in [0,1]`               |transmitter current (:math:`\Delta V /I`)         |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 | - A/m                                            |
|FDEM    |EM1DFM     | 1.0         |- :math:`\kappa = SI`                  | - ppm of primary field                           |
|        |           |             |- :math:`\sigma = S/m`                 | - % of primary field                             |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 | - E: N/C                                         |
|FDEM    |EH3D       |             |- :math:`\kappa = SI` (background only)| - H: A/m                                         |
|        |           |             |                                       | - J: A/m :math:`\! ^2`                           |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 | - E: N/C                                         |
|FDEM    |E3D        |octree       |- :math:`\kappa = SI` (background only)| - H: A/m                                         |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|TDEM    |EM1DTM     |1.0          |:math:`\sigma = S/m`                   | - B: nT, :math:`\mu\!` T or nT                   |
|        |           |             |                                       | - dB/dt: :math:`\mu\!` V, mV or V where V=-dB/dt |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 | - E: N/C                                         |
|TDEM    |H3DTD      |             |- :math:`\kappa = SI` (background only)| - H: A/m                                         |
|        |           |             |                                       | - dB/dt: T/s                                     |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 | - H: A/m                                         |
|TDEM    |TDoctree   |octree       |- :math:`\kappa = SI` (background only)| - dB/dt: T/s                                     |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 | - :math:`Z_{ij}:` V/A                            |
|MT/ZTEM |MTZ3D      |             |- :math:`\kappa = SI` (background only)| - :math:`T_i:` unitless                          |
|        |           |             |                                       | - E: N/C (if option chosen to output)            |
|        |           |             |                                       | - H: A/m (if option chosen to output)            |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 | - :math:`Z_{ij}:` V/A                            |
|MT/ZTEM |E3DMT      |octree ver. 1|- :math:`\kappa = SI` (background only)| - :math:`T_i:` unitless                          |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+
|        |           |             |- :math:`\sigma = S/m`                 | - :math:`Z_{ij}:` V/A                            |
|MT/ZTEM |E3DMT      |octree ver. 2|- :math:`\kappa = SI` (background only)| - :math:`T_i:` unitless                          |
+--------+-----------+-------------+---------------------------------------+--------------------------------------------------+

.. note::
	- Units for potential fields are explicitly stated in manuals
	- Units for DCIP codes should be consistent and were more or less stated in the DCIP2D manual
	- Units for EM1DFM and EM1DTM are explicitly stated in manuals
	- Units for NSEM codes are inferred but likely correct
	- Units for other CSEM codes have been assumed but not verified



GIF Data Sign Conventions and Time-Dependency
---------------------------------------------

Here, we define the sign conventions for various data types and the time-dependence (:math:`\pm i \omega t`) for frequency domain codes. If data are not formatted using the proper convention, it is unlikely that the inversion will be able to fit the data and return meaningful results. The rational for certain sign conventions is explained :ref:`below <signConvention_explained>`.


.. tabularcolumns:: |L|C|C|C|

+--------+-----------+-------------+-------------------------------------------------------------+
|  Type  |  Name     |  Versions   |         Sign Convention                                     |
+========+===========+=============+=============================================================+
|Gravity |GRAV3D     |5.0, 5.1, 6.0| +ve data represents +ve gravity anomalies                   |
+--------+-----------+-------------+-------------------------------------------------------------+
|Gravity |GRAV PDE   |octree       | +ve data represents +ve gravity anomalies                   |
+--------+-----------+-------------+-------------------------------------------------------------+
|Magnetic|MAG3D      |5.0, 5.1, 6.0| +ve data represents +ve magnetic anomalies                  |
+--------+-----------+-------------+-------------------------------------------------------------+
|Magnetic|MAG PDE    |octree       | +ve data represents +ve magnetic anomalies                  |
+--------+-----------+-------------+-------------------------------------------------------------+
|MVI     |MVI        | 3.0         | +ve data represents +ve magnetic anomalies                  |
+--------+-----------+-------------+-------------------------------------------------------------+
|DC/IP   |2D DCIP    |             |:math:`\mathbf{E}=-\nabla V` and :math:`\Delta V = V_N - V_M`|
+--------+-----------+-------------+-------------------------------------------------------------+
|DC/IP   |3D DCIP    |             |:math:`\mathbf{E}=-\nabla V` and :math:`\Delta V = V_N - V_M`|
+--------+-----------+-------------+-------------------------------------------------------------+
|DC/IP   |DCIP octree|octree       |:math:`\mathbf{E}=-\nabla V` and :math:`\Delta V = V_N - V_M`|
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Time-dependency is :math:`+i\omega t`                     |
|FDEM    |EM1DFM     | 1.0         | - Hx, Hy, Hz with Z-axis pointing downward                  |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Time-dependency is :math:`-i\omega t`                     |
|FDEM    |EH3D       |             | - Hx, Hy, Hz with z-axis pointing ???                       |
|        |           |             | - Ex, Ey, Ez with z-axis pointing ???                       |
|        |           |             | - Jx, Jy, Jz with z-axis pointing ???                       |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Time-dependency is :math:`+i\omega t`                     |
|FDEM    |E3D        |octree       |                                                             |
|        |           |             |                                                             |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Hx, Hy, Hz with z-axis pointing downward                  |
|TDEM    |EM1DTM     |1.0          | - dBx/dt, dBy/dt, dBz/dt with Z-axis pointing downward      |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Hx, Hy, Hz with z-axis pointing upward                    |
|TDEM    |H3DTD      |             | - dBx/dt, dBy/dt, -dBz/dt with Z-axis pointing upward       |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Hx, Hy, Hz with z-axis pointing upward                    |
|TDEM    |TDoctree   |octree       | - dBx/dt, dBy/dt, -dBz/dt with Z-axis pointing upward       |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Time-dependency is :math:`-i\omega t`                     |
|MT/ZTEM |MTZ3D      |             |                                                             |
|        |           |             |                                                             |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Time-dependency is :math:`+i\omega t`                     |
|MT/ZTEM |E3DMT      |octree ver. 1|                                                             |
|        |           |             |                                                             |
+--------+-----------+-------------+-------------------------------------------------------------+
|        |           |             | - Time-dependency can be chosen as :math:`\pm i\omega t`    |
|MT/ZTEM |E3DMT      |octree ver. 2|                                                             |
|        |           |             |                                                             |
+--------+-----------+-------------+-------------------------------------------------------------+


.. note::
    - Time-dependency for FDEM codes was inferred from the initial formulation of Maxwell`s equations in the theory sections for each available manual; :math:`\nabla \times E = \mp i\omega B \rightarrow \pm i\omega t` convention. Exceptions: E3DMT ver 2 can be either. EM1DFM explicitly states a dependency of :math:`+i\omega t`.
    - The theoretical background for DCIP2D, DCIP3D and DCIPoctree seem to indicate a :math:`E =-\nabla V` formulation base on the final expression :math:`\nabla \cdot \sigma \nabla V = \nabla \cdot J_s=-I \delta (r)`.
    - Sign conventions for TDEM data were inferred from looking at an example TDoctree data file showing the response over a conductor. The positive decaying Hz and positive decaying dBz/dt indicated that the sign of the dBz/dt data were flipped. This was not the case for dBx/dt and dBy/dt. It is assumed that the same convention is used for H3DTD but I'm not sure. EM3DTM is explicitly stated however.
    - Sign conventions for FDEM data (except EM1DFM) are a mystery right now
    - Sign conventions for MTZTEM data are a mystery right now.


Time-Dependency
^^^^^^^^^^^^^^^

The relationship between a time-dependent function :math:`f(t)` and its corresponding frequency response :math:`F(\omega`) is given by the inverse Fourier transform:

.. math::
	f(t) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} F(\omega) e^{\boldsymbol{\pm i\omega t}} d \omega.

where the choice in sign of :math:`\pm i\omega t` defines the Fourier convention for :math:`F (\omega)`. The choice has ramifications when expressing Maxwell's equations in the frequency domain. In the time domain, Maxwell's equations are given by:

.. math::
	\begin{align}
	\nabla \times \mathbf{e} &= - \frac{\partial \mathbf{b}}{\partial t} \\
	\nabla \times \mathbf{h} &= \mathbf{j} + \frac{\partial \mathbf{d}}{\partial t}
	\end{align}

If the inverse Fourier transform is defined using :math:`+ i\omega t`, then Maxwell's equations in the frequency domain are:

.. math::
	\begin{align}
	\nabla \times \mathbf{E} &= - i\omega \mathbf{B} \\
	\nabla \times \mathbf{H} &= \mathbf{J} + i\omega \mathbf{D}
	\end{align}

where :math:`e^{+i\omega t}` is suppressed. However, if the inverse Fourier transform is defined using :math:`- i\omega t`, then Maxwell's equations in the frequency domain are:

.. math::
	\begin{align}
	\nabla \times \mathbf{E} &= i\omega \mathbf{B} \\
	\nabla \times \mathbf{H} &= \mathbf{J} - i\omega \mathbf{D}
	\end{align}

where :math:`e^{-i\omega t}` is suppressed. As we can see, the phase relationship between :math:`\mathbf{E}` and :math:`\mathbf{B}` in Faraday's law is different in the previous two equations. Similarly for the Ampere-Maxwell law. Thus it is important to know which convention is being used when examining the electric and magnetic fields derived from a particular FDEM code.


.. _signConvention_explained:

Specific Sign Conventions
^^^^^^^^^^^^^^^^^^^^^^^^^

**Magnetics:**

For total magnetic intensity (TMI) data, the sign of the data is determined by whether the secondary magnetic field 'adds to' or 'opposes' the Earth's inducing field; where the Earth's inducing field can be at a variety of orientations depending on latitude and regional variations. In this case, a positive data value indicates that the secondary magnetic field has vector components parallel to the Earth's inducing field; i.e. it 'adds to' the inducing field. In contrast, a negative data value indicates that components of the secondary field are anti-parallel, or 'oppose', the Earth's inducing field.

For amplitude data, a positive value indicates that the magnitude of the total observed magnetic field (:math:`\mathbf{B_p + B_s}`) is larger than the Earth's inducing field (:math:`\mathbf{B_p}`); i.e. :math:`| \mathbf{B_p + B_s} | > |\mathbf{B_p} |`. The opposite is true for negative data values.


**DCIP data:**

In the electrostatic case, the Ampere-Maxwell equation shows that :math:`\nabla \times \mathbf{E} = 0` and that :math:`\mathbf{E}` can be written as the gradient of a scalar potential:

.. math::
	\mathbf{E} = \pm \nabla V.

By taking the divergence of Faraday`s law and substituting the previous expression, the DC resistivity problem is ultimately defined by the following expression:

.. math::

	- \nabla \cdot \sigma (\pm \nabla V) = \nabla \cdot \mathbf{j_e}

As we can see, our choice in the relationship between :math:`\mathbf{E}` and :math:`V` changes the sign convention for the voltage measurements. In the case of UBC GIF codes, we choose :math:`\mathbf{E} = - \nabla V`. By this convention, secondary potentials are positive in the vicinity of positive electric charges and negative in the vicinity of negative electric charges.


**H3DTD and TDoctree data:**

For most of the data columns (Hx, Hy, Hz, dBx/dt, dBy/dt), the data represent the true anomalous field components in the coordinate system that defines the data locations. However, a particular sign convention is used for the dBz/dt component.

The sign convention for dBz/dt can be explained as follows. For coincident loop airborne systems, the true dBz/dt response observed at the center of the receiver coil is negative and decaying during the off-time. However, the decay curves for this component have historically been plotted as positive and decaying. This is done for two reasons. 1) A positive decay curve is analogous to the strength of a decaying inductive response. 2) The raw voltage induced within the receiver coil is in fact positive and decaying. This is because the induced EMF is proportional to -dB/dt. When people first plotted the raw voltages for this component, it was positive and decaying and the convention for plotting dBz/dt data was born.


