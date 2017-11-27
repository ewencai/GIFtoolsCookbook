.. _AtoZNorms:

Lp and Lq Norms
===============

.. ../../../images/LpLqNorms_Linear.png
..    :align: right
..    :figwidth: 100%

Introduced in v6 of the gravity and magnetics codes and available in the EM1DTM code, it is now possible to change the norms in the different part of the regularization.

Most codes thus far have involved the L2 norm (which is a “sum of squares” style of norm), which favors smoothness. The choice of model norm style is based upon prior knowledge. For example, it makes sense to look for simple smooth models when there is no knowledge about subsurface structures. In contrast, the L0 or L1 norm has some different characteristics: it makes blocky models, and outliers are less influential.

The difference between the recovered model and the reference model is calculated at each iteration. The metric that is used can be defined as the sum of the difference (L1), or the sum of the squares of the difference (L2), or some other exponent of the difference. The user-definable exponent is referred to as Lp. For values between 0 and 2, a high value results in smoothly varying models and a low value allows for sparse models.

Similarly, the exponents relating to the gradients in x, y and z are definable through the Lq parameter. For values between 0 and 2, a high value enforces smooth gradients and a low value allows discontinuous gradients, resulting in blocky models.

In the schematic figure below, (Lp, Lq) are (2,2), (0,2), (0,1) and (0,0) respectively. The blue curve is the original model and the red curves are the recovered models.
