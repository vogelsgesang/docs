========
pyflakes
========

Supported Codes
===============

We integrated the following, pre-selected `pyflakes <https://launchpad.net/pyflakes>`_ codes. Need more? Please `let us know <http://quantifiedcode.com/contact>`_!

.. csv-table::
    :header: "Code", "Message"

    "F401", "module imported but unused"
    "F402", "import module from line N shadowed by loop variable"
    "F403", "from module import \*' used; unable to detect undefined names"
    "F404", "future import(s) name after other statements"
    "F811", "redefinition of unused name from line N"
    "F812", "list comprehension redefines name from line N"
    "F821", "undefined name name"
    "F822", "undefined name name in __all__"
    "F823", "local variable name ... referenced before assignment"
    "F831", "duplicate argument name in function definition"
    "F841", "local variable name is assigned to but never used"
