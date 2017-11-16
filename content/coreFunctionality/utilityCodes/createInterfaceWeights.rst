.. _createinterfWeights:

.. include:: <isonum.txt>

Create interface weights for an octree mesh
===========================================

Interaction with the Fortran utility program ``interface_weights`` can be done by creating an *createInterfaceWeight* item. This item will interact with the utility program to create a weight file for the octree cell faces. The input file specifies a tolerance and the weight for the edges. The weights are set to the give edge weight value when the absolute value of the gradient of the model is larger than the tolerance. Weights should be less than 1 to have a sharp boundary and greater than 1 for a smooth boundary. The input file also specifies the number of surface layers and the surface weight value for the x and y faces for those layers. To create, use the menu structure:


**Create** |rarr| **Fortran utility program** |rarr| **Octree utilities** |rarr| **Create interface weights**

.. figure:: ../../../images/createOctreeUtility.png
    :align: center
    :figwidth: 100%


