===============
Query Operators
===============

`Cody` provides a range of query operators to facilitate pattern matching on the syntax tree.


* :ref:`basics`
* :ref:`references`
* :ref:`boolean`
* :ref:`repetition`
* :ref:`matching`
* :ref:`structure`
* :ref:`regex`
* :ref:`matching`

.. _basics:

Basics
======

Operators get invoked by adding a dict to your query that contains a key with
the name of the operator, prefixed by the magic **$** sign. The value corresponding to that key
will then get compiled and passed to the operator function. All other key/value pairs in the dict
will get passed as arguments to the operator. An example:

.. code-block:: yaml

    $store:
      node_type: functiondef
    name : my_function

will match nodes with `node_type = functiondef` and store them in a variable called `my_function`.

Another one:

.. code-block:: yaml

    $repeat:
      node_type: assign
    min: 5
    max: 10

Will match 5 to 10 consecutive `assign` statements.

.. _references:

Storing and Retrieving Sub-Patterns
===================================

$store
------

Stores a matched subtree in a variable

$store_as
---------

$ref
----

.. _boolean:

Boolean Operators
=================

$or
---

$and
----

$not
----

$eq
---

.. _repetition:

Repetition and Concatenation
============================

$concat
-------

$repeat
-------

.. _matching:

Matching Nodes
==============

$match
------

$anything
---------

$empty
------

.. _structure:

Position within the Tree
========================

$first
------

$last
-----

$parent
-------

.. _contains:

$contains
---------

$anywhere
---------

.. _regex:

Regex Matching
==============

$regex
------
