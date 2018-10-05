.. _Fundamentals_Joint:

Data Weighting and Joint Inversion
==================================

Joint inversion inverts two or more datasets simultaneously to recover a unifying physical property model. For example, any combination of MT, ZTEM, FDEM or TDEM data may be inverted jointly to recover a conductivity model. When performing joint inversion, it is important that the data misfit for each individual dataset is appropriately weighted. If this is not done correctly, the inversion will overfit a particular dataset at the expense of others; typically the dataset with the largest number of data observations.

To weight the data appropriately, we let the total data misfit for the inversion (:math:`\phi_d`) be the weighted sum of the data misfits for each dataset, i.e.:

.. math::
    \phi_d = c_1 \phi_d^{(1)} + c_2 \phi_d^{(2)} + \, ... \; = \sum_{k=1}^K c_k \phi_d^{(k)}
    :label: eq_phi_d_again

where :math:`K` is the total number of datasets, :math:`c_k` are the weighting constants and:

.. math::
    \phi_d^{(k)} = \big \| \mathbf{W_d^{(k)}} \big ( \mathbf{d_{obs}^{(k)}} - \mathbb{F^{(k)}}[\boldsymbol{\sigma}] \big ) \big \|^2
    :label:

Thus for dataset :math:`k`:

    - :math:`\mathbf{W_d^{(k)}}` is a diagonal matrix containing the reciprocal of the data uncertainties
    - :math:`\mathbf{d_{obs}^{(k)}}` is the set of field observations
    - :math:`\mathbb{F^{(k)}}` denotes the forward modeling operator.


Weight by number of data
^^^^^^^^^^^^^^^^^^^^^^^^

Using this approach, we weight each dataset based on the number of field observations. Datasets with more field observations given smaller weighting constants :math:`c_k` and visa versa. Let :math:`N_1, \, N_2 , \, N_3, \, ... \, , N_K` be the total number of data observations for datasets 1, 2, 3, ... , :math:`K`, respectively. Where :math:`\widetilde{N}` is the average number of data observations for all datasets, we let:

.. math::
    c_k = \frac{\widetilde{N}}{N_k}


The benefits of this approach are as follows:

    1. the target data misfit for the inversion remains the same; i.e. it is the total number of data observations for all datasets
    2. the inversion no longer fits datasets based on the number of data observations









