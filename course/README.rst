==================
PRL Onboard Course
==================

Introduction
============

This course should guide you from being completely new to computational thermodynamics to up and running in Python with the ability to use, understand, and develop the open-source tools used in the Phases Research Lab.

This course is living and incomplete.

Resources
=========

Texts
-----

The following resources will be used and referred to by authors. See the repo readme for more info on these resources.

* Effective Computation in Physics - Scopatz and Huff
* Density Functional Theory, A Practical Introduction - Sholl and Steckel

Scopatz and Huff will often use the IPython console in code examples. It is suggested to use the IPython Notebooks mentioned in the book (now called `Jupyter Notebooks`_) for the nice graphical interface and feedback. Jupyter Notebooks are very common among scientists and are growing in popularity as a digital lab notebook. This is also how solutions will be provided.

To use it, run `jupyter notebook` to start it from the command line (Windows users can open the app installed with Anaconda), which should open a browser window.

As you go through Scopatz and Huff, try to do all of the exercises. The code examples and files are found at https://github.com/physics-codes/examples

The calculation exercises are not necessary in Sholl and Steckel, but try to follow the math to the best of your ability.

Videos
------

YouTube
~~~~~~~

The PyCon and SciPy annual conferences usually are preceded by good ~3 hour tutorials that are posted on YouTube shortly after the conference.
They are also great resources for becoming more aware of the things people are using Python for and the great variety of packages that are being developed.
Two options for general courses are

* Maxim Belkin: Software Carpentry Scientific Python Course `Part 1 <https://youtu.be/7VO4pUGCcMI>`_ and `Part 2 <https://youtu.be/V5KQxBKtdA8>`_ (SciPy 2017)
* Alternatively, `Trey Hunner: Hands-On Intro to Python for New Programmers <https://www.youtube.com/watch?v=6zu8lrYn6t8>`_ (PyCon 2017)

For tutorials on specific packages that are of interest to our group, see the following tutorials (ordered roughly from most to least generally useful)

* `David Baumgold: Get Started with Git <https://youtu.be/RrdECLvHW6g>`_ (PyCon 2016)
* `Dillon Niederhut: Introduction to Numerical Computing with NumPy <https://www.youtube.com/watch?v=lKcwuPnSHIQ>`_ (SciPy 2017)
* `Ben Root: Anatomy of Matplotlib <https://youtu.be/rARMKS8jE9g>`_ (SciPy 2017)
* `Ondrej Certik, et al.: Symbolic Compution with Python using SymPy (Beginner) <https://youtu.be/AqnpuGbM6-Q>`_ (SciPy 2016)
* `Jonathan Rocher: Analyzing and Manipulating Data with Pandas (Beginner) <https://youtu.be/6ohWS7J1hVA>`_ (SciPy 2016)
* `James Crist: Parallelizing Scientific Python with Dask <https://youtu.be/mbfsog3e5DA>`_ (SciPy 2017)
* `Chalmer Lowe: bokeh: Data Visualization in Python <https://youtu.be/xId9B1BVusA>`_ (SciPy 2017)
* `Aaron Meurer et al.: Automatic Code Generation with SymPy <https://youtu.be/5jzIVp6bTy0>`_ (SciPy 2017)
* `Dillon Niederhut: Cython for Data, Scientists, and Data Scientists <https://youtu.be/FepqwPI6U80>`_ (SciPy 2017)
* `Mike McKerns: Modern Optimization Methods in Python <https://youtu.be/avRx2cdNZmk>`_ (SciPy 2015)

Tutorials on tools and building packages

* `Michael Tom-Wing, Christie Wilson: Introduction to Unit Testing in Python with Pytest <https://youtu.be/UPanUFVFfzY>`_ (PyCon 2016)
* `Eric Holscher: Documenting your project with Sphinx & Read the Docs <https://youtu.be/hM4I58TA72g>`_ (PyCon 2016)
* `Titus Brown, Luiz Irber: Creating, building, testing, and documenting a Python project - a hands-on HOWTO <https://youtu.be/SUt3wT43AeM>`_ (PyCon 2016)

Lynda
~~~~~

`Lynda.com <http://lynda.psu.edu>`_ is free for Penn State students. Some relevant video resources for learning Git and Python are

* `Git Essential Training`_: long (6h), but complete. Has a short introductory quiz to gauge your understanding.
* `Python 3 Essential Training`_: a good survey of all of the basic Python standard library features. Not much for science or numerical computing explicitly.
* `Python Design Patterns`_: once you know the basics, covers some common patterns used to design good libraries.

.. _Jupyter Notebooks: http://jupyter.org
.. _Git Essential Training: https://www.lynda.com/Git-tutorials/Git-Essential-Training/100222-2.html
.. _Python 3 Essential Training: https://www.lynda.com/Python-tutorials/Python-3-Essential-Training/62226-2.html
.. _Python Design Patterns: https://www.lynda.com/Python-tutorials/Design-Patterns-Python/369187-2.html


Schedule
========

The schedule is assignment based. You should proceed by completing the assignments in order and doing the required tasks for each assignment

Initially, the course will be entirely Python-based, but will blend into CALPHAD and DFT.

Everything should be able to be completed on any personal computer except performing DFT calculations with atomate, which currently requires the use of VASP. Because atomate is run on HPCs through a queue, usage will be limited to a single assignment and other DFT assignments will provide raw data as if they were from DFT. Other usage information is directed to the `official atomate documentation`_.

1. Assignment 1: Getting started in Git

   * Scopatz and Huff: chapter 1 and 2 (and install Python, preferably Anaconda_)
   * Scopatz and Huff: chapters 15, 16

2. Assignment 2: Contributing to open-source software

   * Scopatz and Huff: chapter 21

3. Assignment 3: Introduction to pymatgen

   * Scopatz and Huff: chapters 3-6
   * Sholl and Steckel: chapters 1 and 2

4. Assignment 4: atomate (Warning: long and requires HPC)

   * Sholl and Steckel: chapter 3
  
5. Assignment 5: Introduction to pycalphad

   * Scopatz and Huff: chapter 7 and 9
   * xarray_ Overview, FAQ, and do examples
   * Liu

6. Assignment 6: Make a contriubtion to pycalphad

   * Scopatz and Huff: chapters 17-19
   * `reStructuredText reference`_

.. _official atomate documentation: http://pythonhosted.org/atomate/
.. _Anaconda: https://www.continuum.io
.. _xarray: http://xarray.pydata.org
.. _reStructuredText reference: http://restructuredtext.readthedocs.io

Tips
====

1. If you are stuck on anything for more than 15 minutes, it's probably because whatever you are trying to figure out isn't being presented to you in a way you can understand. This is a great time to ask someone a question!



