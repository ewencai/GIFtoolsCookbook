.. _ObjectiveFunction:

The Objective Function
======================

The inverse problem is formulated as the minimization of a model dependent
Objective Function. This Objective Function :math:`\phi(\mathbf{m})` is
written as the weighted sum of two main term, the data misfit :math:`\phi_d` and the
regularization :math:`\phi_m` (equation \ref{eq1})

.. math::
    \phi(\mathbf{m}) = \phi_d(\mathbf{m}) + \beta \phi_m(\mathbf{m})
    :label: ObjFun

-  :math:`\mathbf{m}` is the inversion model at each iteration (also the starting model at the beginning of the inversion).
- :math:`\beta` is a :ref:`trade-off parameter<AtoZBeta>` that controls the relative importance of the regularization compared to the data misfit function.

The Data misfit -  :math:`\phi_d` in :eq:`ObjFun` is express as:

.. math::
    \phi_d(\mathbf{m}) = ||\mathbf{W}_d (\mathbf{F}(\mathbf{m})-\mathbf{d})||^2
    :label: DataMisfit

With the forward operator :math:`\mathbf{F}` relating the model
:math:`\mathbf{m}` to the the geophysical data :math:`\mathbf{d}`. the matrix
:math:`W_d` summarize the estimated noise on each data point. The expected
value for the data misfit is equal to the number of data :math:`nd` for a
target misfit of 1 times the chifactor (user defined).

..    \phi_m(\mathbf{m}) = \alpha_s \int (w_s(\mathbf{r})(m(\mathbf{r})-m_0)^2 \delta v) + \alpha_x \int w_x(\mathbf{r})\left\( \frac{\delta(m(\mathbf{r})-m_0)}{\delta x}\right\)^2 \delta v + \alpha_z \int w_z(\mathbf{r})\left\( \frac{\delta(m(\mathbf{r})-m_0)}{\delta z}\right\)^2 \delta v + \alpha_z \int w_z(\mathbf{r})\left\( \frac{\delta(m(\mathbf{r})-m_0)}{\delta x}\right\)^2 \delta v

The regularizer :math:`\phi_m` in :eq:`ObjFun` itself can be divided in two sections, the smallness and the smoothness:

.. math::
    \phi_m(\mathbf{m}) = \phi_{small}(\mathbf{m}) + \phi_{smooth}(\mathbf{m})
    :label: Regularizer

With:

.. math::
    \phi_{small}(\mathbf{m}) = {\alpha_s} ||\mathbf{W_s}\;\mathbf{R}_s(\mathbf{m}-\mathbf{m}_{ref})||_2^2
    :label: Smallness

- :math:`\phi_{small}` is the Smallness term. It defines how the model can vary from the reference model :math:`\mathbf{m}_{ref}` (:eq:`Smallness`).

And:

.. math::
    \phi_{smooth}(\mathbf{m}) = &{\alpha_x} ||\mathbf{W_x}\;\mathbf{R}_x \; \mathbf{G}_x(\mathbf{m}-\mathbf{m}_{ref})||_2^2 +\\
    &{\alpha_y} ||\mathbf{W_y}\;\mathbf{R}_y \; \mathbf{G}_y(\mathbf{m}-\mathbf{m}_{ref})||_2^2 +\\
    &{\alpha_z} ||\mathbf{W_z}\;\mathbf{R}_z \; \mathbf{G}_z(\mathbf{m}-\mathbf{m}_{ref})||_2^2
    :label: Smoothness

- :math:`\phi_{smooth}` is the Smoothness term. it defines how the gradients in each direction, defined by the matrices  :math:`G_x`,  :math:`G_y` and :math:`G_z`, of the model can vary from the gradient of the reference model (:eq:`Smoothness`).


..    \phi_m(\mathbf{m}) = \alpha_s ||W_s(\mathbf{m}-\mathbf{m}_0)||^p + \alpha_x ||W_x G_x(\mathbf{m}-\mathbf{m}_0)||^q + \alpha_y ||W_y G_y(\mathbf{m}-\mathbf{m}_0)||^q + \alpha_z ||W_z G_z(\mathbf{m}-\mathbf{m}_0)||^q

- The :ref:`weighting matrices<AtoZWeightingMatrix>` :math:`\mathbf{W}_s`, :math:`\mathbf{W}_x`, :math:`\mathbf{W}_y` and :math:`\mathbf{W}_z` are cell-specific weightings for each of these terms. They can combine user-defined confidence models with depth or distance weighting.
- the :ref:`alphas paramters<AtoZalphas>` :math:`\alpha_s`, :math:`\alpha_x`, :math:`\alpha_y`, and :math:`\alpha_z` control how important each of the four terms are relative to each other
- The sparsity weights :math:`\mathbf{R}_s`, :math:`\mathbf{R}_x`, :math:`\mathbf{R}_y` and :math:`\mathbf{R}_z` are defined by the :ref:`lp-norms <AtoZNorms>`.
- In the UBC codes, the option SMOOTH_MOD_DIFF uses the reference model in all terms, while SMOOTH_MOD would only use the reference model in the Smallness term.

In this section, we will explore the effect of these different parameters on the recovered model through a susceptible block in a non-susceptible half-space mapped with a total magnetic ground survey.

.. figure:: ../../../images/InversionFundamentals/model.png
    :align: right
    :figwidth: 100%
