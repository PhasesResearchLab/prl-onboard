================================
Assignment 7: Installing atomate
================================

Objectives
==========
* Install atomate
* Create and run a workflow
* Analyze the results of that workflow using pymatgen

.. note:: There are no solutions for this. Everything should be in the atomate documentation.

.. note:: You need an account on a supercomputing cluster

Tasks
=====

1. Set up a database on mLab

   1. Create an account at https://mlab.com
   2. Create a sandbox database. Name it ``fireworks-db``. Create a user called ``admin`` and give it a password. I suggest using a random string generator as **it will be stored in plain text.**.
   3. Create a second sandbox database. Name it ``materials-db``. Create a user called ``admin`` and give it a password. Create a user called ``readonly`` and also give it a password, checking the readonly box.
   4. Keep this page, usernames, and passwords handy because you will use them shortly. If you go to the main page of your database (the one with the tabs of "Collections", "Users", "Stats", etc. in the middle of the page) the credentials you will need are above the tab section. You'll see connection information such as an address of ``ds035177.mlab.com:35177/materials-db``. The host name you will connect to would be ``ds035177.mlab.com`` and the port would be ``35177``. The db name would be ``materials-db``. 

**COMPLETE THE FOLLOWING ON A SUPERCOMPUTING CLUSTER**. Penn State's ACI might be a good choice.

2. Read the homepage at the `atomate documentation <https://hackingmaterials.github.io/atomate/index.html>`_
3. Work through `the installation <https://hackingmaterials.github.io/atomate/installation.html>`_. Do it by hand the first time as it will help you be able to fix your own problems. Later you can use the semi-automated installer mentioned in the text.
4. Do the `first tutorial <https://hackingmaterials.github.io/atomate/running_workflows.html>`_
5. Do the `Gibbs (Debye) workflow tutorial <https://hackingmaterials.github.io/atomate/gibbs_workflow_tutorial.html>`_

.. _resources:

Resources
=========
- Mathew, K. et al. Atomate: A high-level interface to generate, execute, and analyze computational materials science workflows. Comput. Mater. Sci. 139, 140–152 (2017). `Atomate paper <https://doi.org/10.1016/j.commatsci.2017.07.030>`_

