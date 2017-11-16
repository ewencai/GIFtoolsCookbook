.. _objectFunctionality_index:

Object-Dependent Functionality
==============================

All of the these functions can be accessed through the menus at the top after selecting the object in the GIFtools tree. The main categories presented here are:

- :ref:`data`
- :ref:`mesh`
- :ref:`model`


.. _data:

Data
----

    **General functionality:**

    .. toctree::
        :maxdepth: 1

        data/editDataHeaders
        Delete columns <data/deleteDataColumns>
        Create topography <data/dataCreateTopo>
        Create 3D mesh <data/dataCreateMesh>
        Downsample <data/downsample>        
        Set input/output (i/o) headers <data/setioHeaders>
        Assign uncertainties <data/assignUncertainties>
        Perform a simple mathematical operation <data/constantCalculator>
        Perform column-to-column mathematical operation <data/columnCalculator>
        Add Gaussian noise <data/addNoise>
        Combine like objects <data/combineData>
        Delete data outside of a mesh <data/meshBasedRemoval>
        Calculate a polynomal trend <data/polyTrend>
        View in 3D, table format, or view statistics <data/viewData>
        Export <data/export>


    **Magnetics:**

    .. toctree::
        :maxdepth: 1

        Assign / Edit inducing field <data/editFieldParams>
        Remove IGRF <data/removeIGRF>


    **DC/IP:**
    
    .. toctree::
        :maxdepth: 1

        Add topography to locations <data/applyTopo>
        Apparent resitivity to/from normalized voltage <data/dcipGeoFactor>
        Project DC/IP 3D data onto a 2D lines for DCIP2D inversion <data/dcip3Dto2D>

    **EM:**

    .. toctree::
        :maxdepth: 1

        Extract time / frequency data <data/emTimeExtract>
        View / edit times or frequencies <data/emViewTime>

.. _mesh:

Mesh
----

    .. toctree::
        :maxdepth: 1

        mesh/createConstantModel
        mesh/createActiveCellsModel
        mesh/refineOctree
        View in 3D <mesh/viewMesh>        
        Export <mesh/export>

.. _model:

Model
-----

    .. toctree::
        :maxdepth: 1

        model/createActiveCells
        Set unit name <model/setUnit>
        Perform a simple mathematical operation <model/modelCalculator>
        Add polyhedra from property data <model/addPolyBlock>
        Assign values to air cells <model/assignAirValues>        
        View in 3D, table format, or view statistics <model/viewModel>
        Export <model/export>


