.. _AtoZ_index:

A to Z Examples
===============

What is this?
-------------

A to Z examples is a collection of step by step tutorials for completing projects using GIFtools. Tutorials include: forward modeling and inverting geophysical data, equivalent source processing and demonstrating the extended functionality provided within GIFtools. Each tutorial is broken down into a set of linear steps and makes use of items from the :ref:`recipes <recipe_index>` section. Any files required to complete the tutorials will be provided as needed through download links. By completing the tutorials from A to Z examples, you will be proficient in using GIFtools to complete other projects.

.. figure:: ../../images/TKC_7Steps.png
    :align: right
    :figwidth: 50%

    7-step process applied to TKC kimberlite complex

Tutorials are organized by geophysical method:

    .. toctree::
       :maxdepth: 1

        Gravity <gravity/index>
        Magnetics <magnetic/index>
        Create an octree mesh <exercise1>
        Forward model a survey <exercise2>
        Invert for a model <exercise3>
        Create a model <exercise4>

However, much of the functionality provided within GIFtools is applicable to multiple methods (e.g. adding geological constraints to inversions). To alter a step in any of the tutorials (e.g. use an OcTree mesh instead of a tensor mesh), search the :ref:`recipes <recipe_index>` section or try the search bar.

For consistency, A to Z examples for each geophysical method consider the same geological model; the Tli Kwi Cho (TKC) kimberlite complex in NWT, Canada. `UBC-GIF <https://gif.eos.ubc.ca>`_ has worked extensively on the TKC area. For background about the deposits, the geophysical surveys, and the outcome (including a combined petrophysical model), see the `Case History on EM Geosci <https://em.geosci.xyz/content/case_histories/do27do18tkc/index.html>`_.

.. _AtoZ_TKCbackground:

Tli Kwi Cho (TKC) Background
----------------------------

The TKC kimberlite complex is being used for A to Z examples because the area has been surveyed with a variety of systems (`see here <https://em.geosci.xyz/content/case_histories/do27do18tkc/survey.html>`_) and drilled extensively. As a result, we have a very good understanding of the geological units which make up the deposit, their margins and their physicals properties. The average density, susceptibility and electrical conductivity for geological units at TKC is shown in the table below.

**NOTE:** Density is relative to background

+-------------+--------------+-------------------+---------+-------------------+------------------+
|**Unit**     |Density [g/cc]|Susceptibility [SI]|Remanence|Conductivity [mS/m]|Chargeability [ms]|
+=============+==============+===================+=========+===================+==================+
| Host        |      0       |         0         |         |                   |                  |
+-------------+--------------+-------------------+---------+-------------------+------------------+
|XVK/DO-18    |   -0.24      |     0.002         |         |                   |                  |
+-------------+--------------+-------------------+---------+-------------------+------------------+
|Kimberlite/HK|   -0.24      |         0         |         |                   |                  |
+-------------+--------------+-------------------+---------+-------------------+------------------+
|HK/DO-27     |   -0.24      |     0.006         |         |                   |                  |
+-------------+--------------+-------------------+---------+-------------------+------------------+
|VK/DO-27     |   -0.24      |     0.003         |         |                   |                  |
+-------------+--------------+-------------------+---------+-------------------+------------------+
|PK/DO-27     |   -0.24      |     0.003         |         |                   |                  |
+-------------+--------------+-------------------+---------+-------------------+------------------+
| Till        |   -0.24      |         0         |         |                   |                  |
+-------------+--------------+-------------------+---------+-------------------+------------------+

**Abbreviations:**

    - PK: pyroclastic kimberlite
    - HK: hypabyssal kimberlite
    - VK: volcaniclastic kimberlite
    - XVK: xenocryst-rich volcaniclastic kimberlite










