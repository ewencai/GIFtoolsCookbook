.. _AtoZalphas:

The Alphas Parameters
=====================

The model objective function is part of the equation that is minimised in the inversion process. It consists of four main components; one that defines how the model can vary from the reference model, and one for each of the allowed gradients in the x, y and z directions. Each of these four components has a coefficient that controls their relative importance to each other. These coefficients are denoted by α.
In real-world scenarios, choosing the correct α values can be problematic. To resolve this, α can be transformed into a Length scale, because the allowed deviation and allowed gradient are spatially related. The equation that governs the relationship is:

Here, the length scales Lx, Ly and Lz are in units equal to those of the cell sizes (usually metres). As a rule of thumb, the length scales should be larger than the cell size. A length scale of four or five times the cell size is a good starting point.

.. math::
    L_x = \sqrt{\frac{\alpha_x}{\alpha_s}} \quad L_y = \sqrt{\frac{\alpha_y}{\alpha_s}} \quad L_z = \sqrt{\frac{\alpha_z}{\alpha_s}}

