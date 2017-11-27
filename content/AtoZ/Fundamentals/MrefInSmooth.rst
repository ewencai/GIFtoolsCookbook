.. _AtoZSmoothInDiff:


The SMOOTH_MOD_DIF or SMOOTH_MOD options
========================================

Introduced in v6 of the gravity and magnetics codes, this toggle controls whether the reference model is used in the gradient terms of the model objective function. If the reference model is used in the gradient terms (SMOOTH_MOD_DIF), then sharp boundaries that are present in the reference model will be preserved. If not used (SMOOTH_MOD), the difference to the gradient model will still be minimised, but the boundary is allowed to have a smooth transition.
