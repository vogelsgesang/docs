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

.. code-block:: yaml

  $store:
    node_type: functiondef
  name: my_function

$ref
----

Get a reference to a stored value.

.. code-block:: yaml

  $ref:
    name: my_function

.. _boolean:

Boolean Operators
=================

$or
---

.. code-block:: yaml

  $or:
    -  node_type: functiondef
       id: my_function
    -  node_type: classdef
       id: my_class

$and
----

.. code-block:: yaml

  $and:
    -  node_type: {ref: my_ref_1}
    -  id: {ref: my_ref_2}

$not
----

.. code-block:: yaml

  $not:
    node_type: functiondef

.. _repetition:

Repetition and Concatenation
============================

$concat
-------

Concatenate a series of expressions.

Example:

.. code-block:: yaml

  $concat:
    - node_type: functiondef
    - node_type: classdef

Matches a function definition followed by a class definition.

$repeat
-------

Repeat a given pattern a certain number of times.

Example:

.. code-block:: yaml

  $repeat:
    node_type: assign
  min: 1
  max: 4

Matches a series of 1 to four assign statements.

Parameters:

* **min**: Minimum number of matches. Default: None (will match zero or more occurences)
* **max**: Maximum number of matches. Default: None (will match zero or more occurences)
* **greedy**: Whether the operator should be *greedy*. If set to `True`, it will first match
              expressions with the highest number of repetitions, otherwise with the smallest.

.. _matching:

Matching Nodes
==============

$anything
---------

Will match, well, anything. Use this if you just want to check that a given element is present in
the tree but you don't care what kind of element it actually is.

$empty
------

Will match if the given element in the tree is empty, i.e. if it contains either an empty
dictionary or an empty list.

.. _structure:

Position within the Tree
========================

$first
------

Matches the first element in the current list of elements.

$last
-----

Matches the last element in the current list of elements.

$parent
-------

Provides a reference to the parent element of the current element.

.. warning:: This works only for nodes whose parent node has been actively traversed during the 
             matching operation, and will thus NOT work for the nodes that are in the initial
             list of nodes passed to the regular expression.

.. _contains:

$contains
---------

Matches a node that contains a given regular expression somewhere in its children.

$anywhere
---------

Matches a given expression anywhere in the tree. This operator will recursively descend into the
current node tree and try to produce a match with the given operator.

.. warning:: This operator can be expensive when matching large trees, use with care.

.. _regex:

Regex Matching
==============

$regex
------

Matches the value of a given field against a regular expression.

Example
_______

.. code-block:: yaml

  node_type: functiondef
  name:
    $regex: foo|bar
