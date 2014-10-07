=============
Configuration
=============

Overview
========

QuantifiedCode is configured using a YML file called ``.codecheck``. By default, all code quality modules are activated. However, with your ``.codecheck`` file, you customize your analysis.

You can ...

* Exclude files and folders from the analysis (just like with .gitignore)
* Disable undesired issues / messages
* Configure code quality modules (coming soon)

Activation
==========

Activate your configuration by saving a hidden file named ``.codecheck`` into the ``root`` directory of your repository.

Usage Example
=============

In order to configure a code quality module (e.g., pylint), you have to add an entry to your ``.codecheck`` file. Depending on the module, different options are available. Please check the respective module for configuration details.

.. code:: yaml

    language: python

    pylint:
        disable:
            - C0321 # more than one statement per line
            - E0104 # return outside of function
            - ...

    pep8:
        disable:
            - E0112 # expected an indented block
            - ...

    pyflakes:
        disable:
            - ImportStarUsed
            - UnusedImport
            - ...


Code quality modules
====================

On the following pages, you will find a detailed overview of the available code quality modules and their configuration options.

.. toctree::
    :maxdepth: 2

    modules/pep8
    modules/pyflakes
    modules/pylint
    modules/quantifiedcode

