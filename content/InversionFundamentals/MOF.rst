.. _InversionFun_MOF:

Model Objective Function
========================

The model objective function (:math:`\phi_m`) is where we impose structures on the recovered model. It also acts as a regularizer; i.e. stabilizes the inversion algorithm. GIF programming separates the model objective function into two parts:

.. math::
    \phi_m(\mathbf{m}) = \phi_{small}(\mathbf{m}) + \phi_{smooth}(\mathbf{m})

where

    - :math:`\phi_{small}(\mathbf{m})` is the smallness. The smallness imposes constraints/conditions on the recovered model itself.
    - :math:`\phi_{smooth}(\mathbf{m})` is the smoothness. The smoothness imposes constraints/conditions on the gradients of the recovered model.

The model objective function is continuous but in practice it can be approximated by a discrete function:

.. csv-table::
    :header: Continuous From, Discretized Form
    
    .. math:: \begin{align} \phi_m (\mathbf{m}) &= \alpha_s \int_V \big | \mathbf{W_s (m - m_{ref}) } \big |^p dV \\ &+ \alpha_x \int_V \Bigg | \mathbf{W_x \dfrac{\partial (m - m_{ref})}{\partial \mathbf{x}} } \Bigg |^{q_x} dV \\ &+ \alpha_y \int_V \Bigg | \mathbf{W_y \dfrac{\partial (m - m_{ref})}{\partial \mathbf{y}} } \Bigg |^{q_y} dV \\ &+ \alpha_z \int_V \Bigg | \mathbf{W_z \dfrac{\partial (m - m_{ref})}{\partial \mathbf{z}} } \Bigg |^{q_z} dV \end{align}, .. math:: \begin{align} \phi_m(\mathbf{m}) &= {\alpha_s} ||\mathbf{W_s}\;\mathbf{R}_s(\mathbf{m}-\mathbf{m}_{ref})||_2^2 \\ &+ {\alpha_x} ||\mathbf{W_x}\;\mathbf{R}_x \; \mathbf{G}_x(\mathbf{m}-\mathbf{m}_{ref})||_2^2 \\ &+ {\alpha_y} ||\mathbf{W_y}\;\mathbf{R}_y \; \mathbf{G}_y(\mathbf{m}-\mathbf{m}_{ref})||_2^2 \\ &+ {\alpha_z} ||\mathbf{W_z}\;\mathbf{R}_z \; \mathbf{G}_z(\mathbf{m}-\mathbf{m}_{ref})||_2^2 \end{align}


Parameter Definitions
---------------------

*Click the header for any parameter to get a comprehensive description and an explanation of its impact on the recovered model*

- **Gradient Operators:**

In the continuous form of the model objective function, gradients on the model in x,y and z are denoted by :math:`\partial /\partial x`, :math:`\partial /\partial y` and :math:`\partial /\partial z`. In discrete form, gradients on the model are approximated by applying discrete linear operators :math:`\mathbf{G_x}`, :math:`\mathbf{G_y}` and :math:`\mathbf{G_z}`.

- :ref:`Alpha Parameters: <InversionFun_Alphas>`

Parameters :math:`\alpha_s`, :math:`\alpha_x`, :math:`\alpha_y` and :math:`\alpha_z` are constants set by the user. They balance the relative importance of satisfying conditions on the the smallness and smoothness in x,y and z. A more complete description of the :math:`\alpha` parameters and their impact on the recovered model are presented :ref:`here <InversionFun_Alphas>`.


- :ref:`Weighting Matricies: <InversionFun_Weighting>`

In the discrete formulation, :math:`\mathbf{W}_s`, :math:`\mathbf{W}_x`, :math:`\mathbf{W}_y` and :math:`\mathbf{W}_z` are a set of cell-specific weighting matricies. These matricies affect whether the smallness or gradients of certain cells are penalized more/less than other cells. Weighting is especially important in potential field problems, where the inversion would otherwise place all susceptible/dense materials at or near the surface. A more complete description of the :math:`\weighting matricies` and their impact on the recovered model are presented :ref:`here <InversionFun_Weighting>`.


- :ref:`Reference Models: <InversionFun_Reference>`




- :ref:`Sparse and Blocky Norms: <InversionFun_Norms>`




Best Practices
--------------


:math:`\phi_{smooth}` is the Smoothness term. it defines how the gradients in each direction, defined by the matrices  :math:`G_x`,  :math:`G_y` and :math:`G_z`, of the model can vary from the gradient of the reference model (:eq:`Smoothness`).


..    \phi_m(\mathbf{m}) = \alpha_s ||W_s(\mathbf{m}-\mathbf{m}_0)||^p + \alpha_x ||W_x G_x(\mathbf{m}-\mathbf{m}_0)||^q + \alpha_y ||W_y G_y(\mathbf{m}-\mathbf{m}_0)||^q + \alpha_z ||W_z G_z(\mathbf{m}-\mathbf{m}_0)||^q

- The :ref:`weighting matrices<InversionFun_Weighting>` :math:`\mathbf{W}_s`, :math:`\mathbf{W}_x`, :math:`\mathbf{W}_y` and :math:`\mathbf{W}_z` are cell-specific weightings for each of these terms. They can combine user-defined confidence models with depth or distance weighting.
- the :ref:`alphas paramters<InversionFun_Alphas>` :math:`\alpha_s`, :math:`\alpha_x`, :math:`\alpha_y`, and :math:`\alpha_z` control how important each of the four terms are relative to each other
- The sparsity weights :math:`\mathbf{R}_s`, :math:`\mathbf{R}_x`, :math:`\mathbf{R}_y` and :math:`\mathbf{R}_z` are defined by the :ref:`lp-norms <InversionFun_Norms>`.
- In the UBC codes, the option SMOOTH_MOD_DIFF uses the reference model in all terms, while SMOOTH_MOD would only use the reference model in the Smallness term.

In this section, we will explore the effect of these different parameters on the recovered model through a susceptible block in a non-susceptible half-space mapped with a total magnetic ground survey.

.. figure:: ../../images/InversionFundamentals/model.png
    :align: right
    :figwidth: 100%