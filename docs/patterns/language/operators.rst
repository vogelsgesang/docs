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

For advanced pattern matching, you can make use of special operators in your query. 
These always start with a dollar (**$**) sign to distinguish them from normal query field. 
The value you pass to the operator should again be a valid pattern dict, or for some operators, 
a dictionary containing arguments. An example: The pattern

.. code-block:: yaml

    $store:
      node_type: functiondef
    name : my_function

will store a node with `node_type = functiondef` in the variable `my_function`.

Some operators do not require a pattern dict and will instead accept arguments. 
These **argument-only** are marked in the list below. An example is the `ref` operator,
which you can invoke like this:

.. code-block:: yaml

    $ref:
      name: my_function

This will fetch the tree stored in the variable `my_function`.

Special Cases
-------------

The normal matching operator also accepts some special arguments, which you can provide using the
special **$** field like this:

.. code-block:: yaml

  $ : {match_first : foo}
  foo: {$store : {$anything : {}},name: foo}
  baz: {$ref : {name: foo}}

Here, we specify that the `foo` branch should get matched first, since the value that we generate
there will be used in the `bar` branch below.

.. _references:

Storing and Retrieving Sub-Patterns
===================================

Often you want to store a part of a tree and reuse it somewhere else in your query. The `$store`
operator allows you this. It accepts as a value

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
