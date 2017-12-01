.. _InversionFun_Misfit:

Data Misfit and Uncertainty Estimation
======================================

The data misfit is responsible for ensuring the recovered model predicts data that fits the set of field observations. The data misfit is generally represented as the L2-norm of a weighted residuals between the observed data and the data predicted for a given model:

.. math::
    \phi_d(\mathbf{m}) = \big \| \mathbf{W}_d [ \mathbf{F}(\mathbf{m})-\mathbf{d} ] \big \| ^2

This formulation of the data misfit is comprised of three components: the data predicted for a given model :math:`\big (\mathbf{F (m)} \big )`, the observed data (:math:`\mathbf{d_{obs}})` and the data weighting matrix (:math:`\mathbf{W_d})`.

**Forward modeling operator**:

The forward modeling operator :math:`\mathbf{F(\;\; )}` predicts the data for a given physical property model :math:`\mathbf{m}`. Therefore, the misfit is a function which depends directly on a particular model.

**Observed Data:**

The set of field observations which are being inverted is represented by :math:`\mathbf{d_{obs}}`.

**Data weighting matrix:**

:math:`\mathbf{W_d}` is a matrix which weights the residuals between the observed data and the predicted data for a given model. :math:`\mathbf{W_d}` weights the residuals based on the uncertainties on the data. The :math:`\mathbf{W_d}` matrix is used for two reasons:

	1) If the observed data span several orders of magnitude, we want to make sure that the inversion doesn't focus on fitting the large values at the expense of the small values.
	2) It is instrumental in providing a reasonable stopping criteria (link) for the inversion.

GIF codes assume that the errors are independent and Gaussian. In this case, the uncertainties are estimations of the standard deviations of random noise on the data and :math:`\mathbf{W_d}` is a diagonal matrix of the form:

.. math::
	\mathbf{W_d} = \begin{bmatrix} 1/\sigma_1 & & & \\ & 1/\sigma_2 & \\ & & \ddots & \\ & & & 1/\sigma_N \end{bmatrix}

where :math:`\sigma_i` is the standard deviation of random noise on data point :math:`i`. 

.. _InversionFun_Misfit_Properties:

Properties of the Data Misfit
-----------------------------







..If the noise on our data are independent and Gaussian, and the assigned uncertainties are correct, then the predicted data fits the observed data to an appropriate tolerance when :math:`\phi_d` equals the number of data; that is, the inversion fits the signal without fitting the noise (over-fitting).

.. _InversionFun_Misfit_Practices:

Best Practices
--------------








