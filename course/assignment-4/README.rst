=======================================
Assignment 4: Introduction to pycalphad
=======================================

Objectives
==========
* Use pycalphad to calculate properties and phase diagrams using thermodynamic databases
* Improve understanding of phase diagrams
* Explore CALPHAD models

.. note:: The assignment solutions are in a Jupyter notebook. If you want to submit your assignment, that format makes it easy to work in and submit.


Tasks
=====

1. Ensure pycalphad is `installed <https://pycalphad.org/docs/latest/INSTALLING.html>`_. For this you will need at version ``0.5.2``. If this version is not available, please install the development version.
#. Open the `pycalphad API documentation <https://pycalphad.org/docs/latest/api/modules.html>`_ in your browser as well as the `pycalphad examples`_. The rest of this assignment can be completed by using and adapting the code in the examples and referring to the API documentation for more information.
#. Start up an interactive Python interpreter (or, preferably, a Jupyter notebook) and create a pycalphad Database from the ``Ag-Bi-Cu-Pb-Sb-Sn-nist-solders.tdb`` thermodynamic database in this directory.
#. The Database object you just created has a ``phases`` attribute that is a dictionary. Print this dictionary. The keys are the phase names and the values are ``Phase`` objects. Each phase object has a ``constituents`` attribute that returns a tuple of the sublattice model for that phase. Print the sublattice model of the ``BCC_A2`` phase and confirm that the sublattice model is ``((CU, SN), (VA))``. Note that the sublattices are wrapped as ``frozensets``. A ``frozenset`` is an immutable version of ``set``.
#. The ``SN-PB`` system.

   a. The tin-lead system is a simple eutectic system with only three phases. Import ``binplot`` from pycalphad and use the ``binplot`` function to plot the binary phase diagram of the ``SN-PB`` system described in the database you created. Use the phases ``['LIQUID', 'BCT_A5', 'FCC_A1']``. Use conditions ``P=101325, T=(300, 700, 5), X(SN)=(0,1,0.005)``. Identify each single and two phase region. **Remember to use ``%matplotlib inline`` magic if you are using a Jupyter Notebook!**
   b. Use ``calculate`` from pycalphad to calculate Gibbs free energies for each of these phases. Use the xarray Dataset returned from the ``calculate`` function and matplotlib to plot the free energy curves as a function of composition. Do this at 400 K, 450 K, 475 K and 600 K. Try to use the ``pycalphad.plot.utils.phase_legend`` function to create a phase legend, see cell 6 in the `pycalphad binary examples <https://github.com/pycalphad/pycalphad/blob/develop/examples/BinaryExamples.ipynb>`_.

#. The ``BI-PB`` binary system.

   a. Like before, would like to plot a phase diagram. This time, there might be more stable phases and we would like to specify by hand. Write a function (possibly called ``filter_active_phases``) to take a pycalphad Database and a list of compositions and return a list of only active phases. An active phase can be defined by a phase that has at least one of the desired components in each sublattice. E.g. a sublattice model of ``((BI,SN), (PB,SN))`` is valid for the components ``BI-PB-VA``, but the sublattice model ``((BI,SN), (SN))`` is not because the second sublattice does not contain any of the components. If you have done this right, running the function should return ``['RHOMBO_A7', 'LIQUID', 'HCP_A3', 'FCC_A1', 'BCT_A5']`` for ``BI-PB-VA`` components. *Hint: use ``set`` methods*
   b. Perform an ``equilibrium`` calculation with pycalphad using the active phases from your function and the conditions ``P=101325, T=(300, 700, 10), X(PB)=(0,1,0.02)``. In addition, pass Store the result in a variable, such as ``eq_result``.
   c. Plot the binary phase diagram, but instead of using binplot, which will run another equilibrium calculation, import ``eqplot`` (``from pycalphad.plot.eqplot import eqplot``) and simply pass in the Dataset returned from the equilibrium calculation.
   d. Previously we calculated and plotted Gibbs free energy for each phase using ``calculate``. We can use ``calculate`` to give us properties for individual phases, but often equilibrium properties are of interest. Use ``equilibrium`` to calculate and plot the equilibrium free energy as a function of composition at 425 K. Bonus: plot the free energies of the phases on top of this plot.

#. The ``DO3`` phase.

   a. The phases we have looked at so far have had very simple sublattice models. The DO3 sublattice model is ``((CU, SN), (CU, SN))`` with sublattice site ratios of ``(0.75, 0.25)``. That means there can be four different endmembers (an endmember has no mixing within sublattices) of this phase, pure Cu and pure Sn (``((CU), (CU))`` and ``((SN), (SN))``), ``CU-25SN`` (``((CU), (SN))``), and ``SN-25CU`` (``((SN), (CU))``). Then with mixing, the entire free energy surface between these endmembers can be calculated. Use ``calculate`` to plot the free energy surface of this phase at 500 K and find the endmembers.
   b. (TODO) On Brandon's Jupyter notebooks repository, there is a thermodynamics folder that contains a free energy surface that interactively changes with temperature

#. The ``AG-BI-CU`` system.

   a. Finally, we will look at a ternary system. pycalphad supports arbitrarily large multicomponent systems. To save time, a precalculated Ag-Bi-Cu ternary system from 300 K to 1600 K. Use xarray's ``open_dataset`` function to create a Dataset from the ``Ag-Bi-Cu-eq.nc`` file in this folder.
   b. Select several temperature slices (with the Dataset methods) of that ternary Dataset. Use the same ``eqplot`` function as earlier to plot these temperatures slices as isotherms.

.. _resources:

Resources
=========
- `pycalphad examples`_
- `pycalphad paper <http://doi.org/10.5334/jors.140>`_


.. _pycalphad examples: https://github.com/pycalphad/pycalphad/tree/develop/examples
