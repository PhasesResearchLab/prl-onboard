==================================================
Assignment 2: Contributing to open-source software
==================================================

Objectives
==========

* Get familiar with the pycalphad repo and API
* Practice branching
* Submit a pull request to pycalphad and have it be reviewed

Tasks
=====
1. Go to the `pycalphad repository`_
#. Use the Fork button to create a fork of the pycalphad repo as your repository on GitHub
#. Clone this forked pycalphad repo to your computer
#. Do one of the following:

  a. Fix typos in the documentation

    1. Checkout the develop branch, then create and checkout a new branch called 'fix-typos'. This branch should share the same HEAD as the develop branch
    #. For each file in the pycalphad/pycalphad folder (e.g. Model.py) and sub folders (e.g. core, io)
    #. Look at each of the docstrings and look for any typos. Fix any typo you find. 
    #. Try to understand what each file is for: e.g. Model.py is for representing the model of each phase as a polynomial with the SymPy library. Don't worry if you don't understand the packages and what is actually going on.
    #. Stop when you've found a couple typos.

5. Commit and push your changes to your fork. Use `good messages`_ and follow the pycalphad conventions by prepending the subject with the correct tag, ``DOC:``, ``FIX:``, ``ENH:``...
#. Open a pull request on GitHub from your branch onto the pycalphad develop branch
#. Use GitHub to `request <https://help.github.com/articles/requesting-a-pull-request-review/>`_ @bocklund to review the PR
#. Fix any feedback with either new commits or by changing the old ones as appropriate. For changing your old commits, you can either use `git commit --amend` or commit regularly and use interactive rebasing to squash additional commits together 
#. Delete your branch locally and on GitHub once your PR has been merged


Resources
=========
* `GitHub help pages`_
* `git - the simple guide`_
* `git merge vs rebase`_
* `git remotes <https://betterexplained.com/articles/aha-moments-when-learning-git/#Understand_local_vs_remote>`_ from BetterExplained (several gems on this page)
* `Git book`_ (advanced)

.. _pycalphad repository: https://github.com/pycalphad/pycalphad
.. _pyformat: https://pyformat.info/
.. _old format: https://docs.python.org/2/library/stdtypes.html#string-formatting
.. _new format: https://docs.python.org/3/library/string.html#string-formatting
.. _good messages: https://chris.beams.io/posts/git-commit/
.. _git - the simple guide: http://git.huit.harvard.edu/guide/
.. _git merge vs rebase: https://www.atlassian.com/git/tutorials/merging-vs-rebasing
.. _Git book: https://git-scm.com/book/en/v2

