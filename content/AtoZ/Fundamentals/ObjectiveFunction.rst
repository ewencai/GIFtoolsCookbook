.. _ObjectiveFunction:

The Objective Function
======================

The inverse problem is formulated as the minimization of a model dependent Objective Function. This Objective Function :math:`\phi(\mathbf{m})` is written as the weighted sum of two main term, the data misfit $\phi_d$ and the regularization :math:`\phi_m$` (equation \ref{eq1})

.. math::
    \phi(\mathbf{m}) = \phi_d(\mathbf{m}) + \beta \phi_m(\mathbf{m})
    :label: ObjFun

-  :math:`\mathbf{m}` is the inversion model at each iteration (also the starting model at the beginning of the inversion).
- :math:`\beta` is a :ref:`trade-off parameter<AtoZBeta>` that controls the relative importance of the regularization compared to the data misfit function.

The Data misfit -  :math:`\phi_d` in :eq:`ObjFun` is express as:

.. math::
    \phi_d(\mathbf{m}) = ||W_d (F(\mathbf{m})-\mathbf{d})||^2
    :label: DataMisfit

With F the forward operator for the geophysical survey. the matrix :math:`W_d` summarize the estimated noise on each data point. The expected value for the data misfit is equal to the number of data :math:`N_d` for a target misfit of 1 times the chifactor (user defined).

..    \phi_m(\mathbf{m}) = \alpha_s \int (w_s(\mathbf{r})(m(\mathbf{r})-m_0)^2 \delta v) + \alpha_x \int w_x(\mathbf{r})\left\( \frac{\delta(m(\mathbf{r})-m_0)}{\delta x}\right\)^2 \delta v + \alpha_z \int w_z(\mathbf{r})\left\( \frac{\delta(m(\mathbf{r})-m_0)}{\delta z}\right\)^2 \delta v + \alpha_z \int w_z(\mathbf{r})\left\( \frac{\delta(m(\mathbf{r})-m_0)}{\delta x}\right\)^2 \delta v

The regularizer :math:`\phi_m` in :eq:`ObjFun` itself can be divided in two sections, the smallness and the smoothness:

.. math::
    \phi_m(\mathbf{m}) = \phi_{small}(\mathbf{m}) + \phi_{smooth}(\mathbf{m})
    :label: Regularizer

With:

.. math::
    \phi_{small}(\mathbf{m}) = \alpha_s ||W_s(\mathbf{m}-\mathbf{m}_0)||^p
    :label: Smallness

- :math:`\phi_{small}` is the Smallness term. It defines how the model can vary from the reference model :math:`\mathbf{m}_0` (:eq:`Smallness`).

And:

.. math::
    \phi_{smooth}(\mathbf{m}) =  \alpha_x ||W_x G_x(\mathbf{m}-\mathbf{m}_0)||^q + \alpha_y ||W_y G_y(\mathbf{m}-\mathbf{m})_0)||^q + \alpha_z ||W_z G_z(\mathbf{m}-\mathbf{m}_0)||^q
    :label: Smoothness

- :math:`\phi_{smooth}` is the Smoothness term. it defines how the gradients in each direction, defined by the matrices  :math:`G_x`,  :math:`G_y` and :math:`G_z`, of the model can vary from the gradient of the reference model (:eq:`Smoothness`).


..    \phi_m(\mathbf{m}) = \alpha_s ||W_s(\mathbf{m}-\mathbf{m}_0)||^p + \alpha_x ||W_x G_x(\mathbf{m}-\mathbf{m}_0)||^q + \alpha_y ||W_y G_y(\mathbf{m}-\mathbf{m})_0)||^q + \alpha_z ||W_z G_z(\mathbf{m}-\mathbf{m}_0)||^q

- The :ref:`weighting matrices<AtoZWeightingMatrix>` :math:`W_s`, :math:`W_x`, :math:`W_y` and :math:`W_z` are cell-specific weightings for each of these terms. They can combine user-defined confidence models with depth or distance weighting.
- the :ref:`alphas paramters<AtoZalphas>` :math:`\alpha_s`, :math:`\alpha_x`, :math:`\alpha_y`, and :math:`\alpha_z` control how important each of the four terms are relative to each other
- The exponents :math:`p` and :math:`q` are defined by the :ref:`Lp and Lq norms <AtoZNorms>`.
- In the UBC codes, The option SMOOTH_MOD_DIFF uses the reference model in all terms, while SMOOTH_MOD would only use the reference model in the Smallness term.
