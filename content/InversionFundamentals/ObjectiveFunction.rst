.. _InversionFun_ObjectiveFunction:

The Objective Function
======================

Geophysical inversion recovers a physical property model which fits the data and has geologically reasonable structures. But how is this done in practice? The majority of geophysical inversion algorithms work by minimizing an objective function (:math:`\phi`) with respect to the physical property model (:math:`\mathbf{m}`):

.. math::
    \phi(\mathbf{m}) = \phi_d(\mathbf{m}) + \beta \phi_m(\mathbf{m})
    :label: ObjFun

This is sometimes referred to as "penalty-based optimization"; that is, the objective function is large if the model doesn't fit the data and/or has implausible structures. The objective function is comprised of three components: the :ref:`data misfit <InversionFun_Misfit>` (:math:`\phi_d`), the :ref:`model objective function <InversionFun_MOF>` (:math:`\phi_m`) and the :ref:`trade-off parameter <InversionFun_Beta>` (:math:`\beta`).

.. note:: Click any of the following subheaders for a comprehensive description.

:ref:`Data misfit: <InversionFun_Misfit>`
-----------------------------------------

The data misfit is responsible for ensuring the recovered model predicts data that fits the set of field observations. The data misfit is given by:

.. math::
    \phi_d (\mathbf{m}) = \big \| \mathbf{W}_d [ \mathbf{F}(\mathbf{m})-\mathbf{d_{obs}} ] \big \| ^2

A detailed explanation of the data misfit can be found :ref:`here <InversionFun_Misfit>`.

:ref:`Model Objective Function: <InversionFun_MOF>`
---------------------------------------------------

The model objective function ensures that the recovered model contains plausible/imposed geological structures. The model objective function is given by:

.. math::
    \begin{align}
    \phi_m (\mathbf{m}) &= \alpha_s \int_V \big | \mathbf{W_s (m - m_{ref}) } \big |^p dV \\
    &+ \alpha_x \int_V \Bigg | \mathbf{W_x \dfrac{\partial (m - m_{ref})}{\partial \mathbf{x}} } \Bigg |^{q_x} dV \\
    &+ \alpha_y \int_V \Bigg | \mathbf{W_y \dfrac{\partial (m - m_{ref})}{\partial \mathbf{y}} } \Bigg |^{q_y} dV \\
    &+ \alpha_z \int_V \Bigg | \mathbf{W_z \dfrac{\partial (m - m_{ref})}{\partial \mathbf{z}} } \Bigg |^{q_z} dV
    \end{align}

A detailed explanation of the model objective function can be found :ref:`here <InversionFun_MOF>`.

:ref:`Trade-off Parameter: <InversionFun_Beta>`
-----------------------------------------------

The trade-off parameter (:math:`\beta`) weights the relative contribution of :math:`\phi_d (\mathbf{m})` and :math:`\phi_m (\mathbf{m})` towards the objective function. It determines how much emphasis we put on fitting the data and how much emphasis we put on imposing structures. A detailed explanation of the trade-off parameter can be found :ref:`here <InversionFun_Beta>`.




