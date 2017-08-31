======================
Assignment 1 Solutions
======================


1. Editors
==========

1.1 Which text editor should I use?
-----------------------------------

`Editor wars`_ have long existed in plain text command line editors. If you are coming from a background where you've only edited text in graphical editors you probably don't think this is a big deal and you just want to know what program lets you type stuff in and navigate with the arrow keys. For that, ``nano`` will work well.

More advanced editors exist with additional funcitonality that you might not yet realize you wanted in a text editor. Mainly, users of ``vim`` and ``emacs`` which are both widely popular yet have very different workflows exist. `Wikipedia covers the details in more depth`_ but I will summarize each here:

* ``vim`` is a modal editor. There are two modes command mode and insert mode. You start in command mode where you quit with ``:q``, save and quit by typing ``:wq`` or quit without saving with ``:q!``. To enter insert mode use the ``i`` key. To get out of insert mode back into command mode, use the ``esc`` key. 

* ``emacs`` is a highly customizable editor. Emacs is generally opened once and left open, then you open files inside of it to edit. All of the commands such as saving and quitting (``ctrl+x``, ``ctrl+c``) use a combination of keystrokes with modifiers such as the ``ctrl`` or meta (usually ``alt``/``option``) keys. Emacs has many plugins such as `org mode`_. 

Personally, I find that modal editing in vim is more useful for me. I often have large output files that I need to reformat (e.g. by deleting a few columns and adding another one in a csv file) and I can create a one-off macro in vim just by hitting ``q`` to record my steps. I also don't like reaching with my pinky finger in emacs, but `spacemacs`_ is a custom, prepackaged emacs customizaiton that has all of the nice commands that emacs offers (you can get to them by hitting the *space* key) combined with the vim keybindings (``evil`` mode). 

Most people in the Phases Resarch Lab use vim. If you feel like you already have enough things to learn, just use ``nano`` which has any commands you would ever need (saving and quitting) displaed on screen at all times. 

.. _Editor wars: https://xkcd.com/378/
.. _Wikipedia covers the details in more depth: https://en.wikipedia.org/wiki/Editor_war
.. _org mode: http://orgmode.org
.. _spacemacs: http://spacemacs.org


1.2 Which code editor should I use?
-----------------------------------

Like text editors, there are many options for code editors. I'll summarize a few options here. All of these are cross platform.

* ``Jupyter notebooks`` (recommended) come with Anaconda or are installable from the command line with ``conda install jupyter`` or ``pip install jupyter``. Jupyter notebooks are very popular in science. They can be version controlled on GitHub and the plots and images you put inside them are rendered online for you to see. For this reason, the Python homework solutions are writting as Jupyter notebooks.

* ``Spyder`` comes with the installation of Anaconda. It has a MATLAB-like interface and is built mostly around writing scripts and Python interactively and seeing your variables just like in MATLAB.

* ``PyCharm`` is a full on Python IDE. It has many great features for developing Python packages. You can get a license for the `professional edition`_ which has more features for free with a ``.edu`` email. Note that JetBrains (PyCharm developers) have recently released PyCharmEdu which is a *different product*. It has git integration built in and it is highly recommended that you use this if you are interested in developing Python software.

* ``Sublime Text`` is simple but powerful text and code editor. 

* ``Visual Studio Code`` is a free and open source text and code editor from Microsoft with a large and growing community around it. There are many good plugins and git integration.

2. Git
======

2.1 How often should I commit?
------------------------------

How often to ``git commit`` is subjective. The power of git is to be able to track, see, and go to any commit in your history. You can use ``git rebase`` to remove commits, which is relatively easy ``squash`` commits and combine them (easy) or add new commits (harder). A good rule of thumb is to have each commit correspond to one logical change and have the commit message well describe what changed. Chris Beams wrote a good article on `writing good commit messages`_. 

Thus the suggested workflow is to 

1. Commit each small logical change that you think you may want to undo later
2. When you are done making changes for a session, look at your commit history and see if any of your commits could be combined into larger chunks. Use ``git rebase -i`` (`rebase tutorial`_) to squash any edits together to make a more cohesive story.
3. Push your changes

As you get more comfortable and start using git more, you'll develop your own style and a good feel for when to commit. At that point, you probably will not have to do step 2 very often. 

.. note: If you are contributing to an open source project, sometimes that project will have guidelines for how to commit. For example pycalphad tries to `label commit messages`_ with what kind of change it is e.g. DOC, ENH, FIX for docuementation changes, new features, and bug fixes, respectively.

.. _professional edition: https://www.jetbrains.com/student/
.. _writing good commit messages: https://chris.beams.io/posts/git-commit/
.. _rebase tutorial: https://robots.thoughtbot.com/git-interactive-rebase-squash-amend-rewriting-history
.. _label commit messages: https://github.com/pycalphad/pycalphad/commits/develop
