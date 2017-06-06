======================================
Assignment 3: Introduction to pymatgen
======================================

Objectives
==========
* Install pymatgen
* Make and explore structures
* Access the Materials Project API and website
* Gain insight on practical usage of containers, control flow, loops, functions, and objects

.. note:: The assignment solutions are in a Jupyter notebook. If you want to submit your assignment, that format makes it easy to work in and submit.


Tasks
=====

1. `Install pymatgen`_ (reccomended: install into a virtual environment. See `resources`_)

    a. Go to the `Materials Project website`_, login, navigate to the Dashboard (top right) and generate an API key. Copy this key. 
    b. Create a ``.pmgrc.yaml`` file in your home directory. Note the leading period. Depending on your operating system, this can cause the file to become hidden, but it is still there. In the file you created, enter the following: ``PMG_MAPI_KEY: MY_KEY_HERE``, where you replace ``MY_KEY_HERE`` with the API key you generated and copied.

#. Open up an interactive Python interpreter (or Jupyter notebook) and go through the `pymatgen quick start`_ examples. Pay particular attention to the instance of the ``Structure`` class (rather than ``Element`` or ``Molecule``). Since our group deals primarily with infinite crystalline lattices, we use pymatgen structures almost exclusively.
#. Create the following ``Structures`` from ``Lattices``. Instead of using the convience class methods e.g. ``Lattice.cubic``, create them from basis vectors. Print the volumes and densities of the structures after you create them to check yourself. The API documentation for these classes may be helpful (see `resources`_). Pay attention to the units! You are encourage, but not required to use ``Structure.to('POSCAR')`` (or ``CIF``) and then load the file into something like VESTA_ (free) or CrystalMaker (commercial).

    a. Po. Simple cubic with lattice parameter of 335 pm
    #. Fe. Body centered cubic with lattice parameter of 2.866 Angstrom
    #. Al. Face centered cubic with volume of 65.89 cubic Angstrom
    #. NaCl. Rock salt structure. Use the ``Lattice.cubic`` staticmethod and a lattice parameter of 5.6402 Angstrom
    #. Ti. Hexagonal. For this, you can use the ``hexagonal`` staticmethod. Try to look up the correct lattice parameter by browsing the Materials Project. It's highly suggested to plot this and convince yourself that the answer is correct. For best results, turn on space filling and increase the boundary to see the close packed structure.

#. Now that you have some appreciation for the tedious creation of structures from lattices, even for pure elements, you might imaging that `'there must be a better way'`_. You may have noticed on the Materials Project that there are many different spacegroups. Spacegroups define different symmetry elements in infinite 2D or 3D lattices and are useful for both understanding and predicting properties and useful in a practical sense. Make the following structures from spacegroups (note, if not given, you're intended to look them up)

    a. NaCl has the spacegroupm F-m3-m, where an Na can be found at (0,0,0) and Cl at (0.5,0.5,0.5). Make a ``Structure`` object directly from the spacegroup and atom positions (don't make a ``Lattice``). Look up the API to do this in the pymatgen documentation. Take note that You only have to enter one of each element, unlike in the problem above. Explain why this is.
    #. Pick a relatively complex (3 or more component) metal or oxide structure from the Materials Project and create it from the spacegroup. Optionally, visualize it in VESTA_ to verify that you constructed it correctly.

#. We've now streamlined ``Structure`` generation, but we can do better still. Using the Materials Project API, we can directly access the structures that we want and modify them from there. Read through the couple examples at the pymatgen `REST API`_ and find the actual API documentation and skim it. Then do the following using ``MPRester``:

    a. Get the ``Structure`` object for ``mp-134``. Print it and compare it to the structure for the same material you made before. What is different? Why?
    #. Get the energy of ``mp-134``
    #. Get all of the energies for C (carbon) structures as a dictionary
    #. Write a function that takes that dictionary and makes a list of energies (in any order)
    #. Do the same as above, except use a list comprehension instead of a function
    #. What are the drawbacks of storing the energies in this way? Are there drawbacks for storing the data as two lists of ids and energies?

#. Finally, we will practice using some of the methods of ``Structure`` objects to transform them. You are expected to read the documentation to see what these do. If the documentation is unclear, try clicking the [Source] button on the right to see the actual Python code. Print the result of each transformation to prove to yourself that you did it correctly. Note that some transformations modify the ``Structure`` object and have no return value while others the return the new object, leaving the original unchanged. You should keep track of this and make sure to update the same structure the whole way through, applying all of the transformations to the same structure.

    a. Create a ``Structure`` of strontium ferrite, ``mp-510624``. What is the chemical formula? What is the volume of the structure? The density?
    #. Look at the band structure and band gap for that structure on the Materials Project website. Is this a metal, semiconductor or an insulator?
    #. Scale the volume to 56.965 cubic Angstrom
    #. Replace all of the Fe species with Co in one step
    #. Make a 2x2x2 supercell
    #. Scale the volume up by 10%
    #. Import and create a ``SpacegroupAnalyzer`` from ``pymatgen.symmetry.analyzer`` with your structure. Print the spacegroup symbol
    #. Replace one of Co with an Fe. What is the chemical formula? What is the spacegroup symbol of this structure?
    #. Break the symmetry with a perturbation of 0.1 Angstrom. What is the spacegroup symbol of this structure?
    #. Explain what the difference is between mutable and immutable objects. What was the implication for these problems?


.. _Install pymatgen: http://pymatgen.org/#getting-pymatgen
.. _Materials Project website: https://materialsproject.org
.. _pymatgen quick start: http://pymatgen.org/#quick-start
.. _properties: https://www.programiz.com/python-programming/property
.. _VESTA: http://jp-minerals.org/vesta/en/
.. _'there must be a better way': https://www.youtube.com/watch?v=wf-BqAjZb8M


.. _resources:

Resources
=========
- Make an `Anaconda virtual environment`_ (recommended) or make on in `virtualenv`_
- pymatgen tutorial for `making structures`_
- pymatgen tutorial for `REST API`_

.. _Anaconda virtual environment: https://conda.io/docs/using/envs.html
.. _virtualenv: http://python-guide-pt-br.readthedocs.io/en/latest/dev/virtualenvs/
.. _making structures: http://pymatgen.org/usage.html#structures-and-molecules
.. _REST API: http://pymatgen.org/usage.html#pymatgen-matproj-rest-integration-with-the-materials-project-rest-api


