.. _AtoZalphas:

The Alphas Parameters
=====================

.. math::
    \phi_m(\mathbf{m}) = \phi_{small}(\mathbf{m}) + \phi_{smooth}(\mathbf{m})
    :label: Regularizer2

With:

.. math::
    \phi_{small}(\mathbf{m}) = \color{blue}{\alpha_s} ||W_s(\mathbf{m}-\mathbf{m}_0)||^p
    :label: Smallness2

And:

.. math::
    \phi_{smooth}(\mathbf{m}) =  \color{blue}{\alpha_x} ||W_x G_x(\mathbf{m}-\mathbf{m}_0)||^q + \color{blue}{\alpha_y} ||W_y G_y(\mathbf{m}-\mathbf{m}_0)||^q + \color{blue}{\alpha_z} ||W_z G_z(\mathbf{m}-\mathbf{m}_0)||^q
    :label: Smoothness2

The model objective function is part of the equation that is minimised in the inversion process. It consists of four main components; one that defines how the model can vary from the reference model, and one for each of the allowed gradients in the x, y and z directions. Each of these four components has a coefficient that controls their relative importance to each other. These coefficients are denoted by α.
In real-world scenarios, choosing the correct α values can be problematic. To resolve this, α can be transformed into a Length scale, because the allowed deviation and allowed gradient are spatially related. The equation that governs the relationship is:

Here, the length scales Lx, Ly and Lz are in units equal to those of the cell sizes (usually metres). As a rule of thumb, the length scales should be larger than the cell size. A length scale of four or five times the cell size is a good starting point.

.. math::
    L_x = \sqrt{\frac{\alpha_x}{\alpha_s}} \quad L_y = \sqrt{\frac{\alpha_y}{\alpha_s}} \quad L_z = \sqrt{\frac{\alpha_z}{\alpha_s}}

Example of the effect of :math:`\alpha_s` on a block in a half-space example
----------------------------------------------------------------------------


.. figure::
     ../../../images/InversionFundamentals/Inversion_Fundamentals_AlphaS_Znormal.png
    :align: right
    :figwidth: 100%

In this example, We see that decreasing :math:`\alpha_s` enforces the smoothness over the smallness term, or increases the length scales, effectively augmenting the smoothness of the recovered models.

Example of the effect of :math:`\alpha_x,\alpha_y,\alpha_z` on a block in a half-space example
-------------------------------------------------------------------------------------------------



.. .. figure::
..      ../../../images/InversionFundamentals/invFund_alpha_x_y_Znormal.png
..     :align: right
..     :figwidth: 100%

.. .. figure::
..      ../../../images/InversionFundamentals/invFund_alpha_z_Ynormal.png
..     :align: right
..     :figwidth: 100%

In this example, We see that increasing :math:`\alpha_x,\alpha_y,\alpha_z` enforces the smoothness over the smallness term, or increases the length scales, effectively augmenting the smoothness of the recovered models in the desired direction.
