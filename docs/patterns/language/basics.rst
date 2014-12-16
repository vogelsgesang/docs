==============
Basic Tutorial
==============

Let's get started writing code patterns! Before we dive into the details of `Cody`, let's quickly
review what exactly we're working with:

Abstract Syntax Trees
=====================

`Cody` performs queries over so-called **abstract syntax trees**, which are a tree representation
of a source code file. As an example, let's look at the Python code

.. code-block:: python

    a = b

This code translates to the following AST:

.. code-block:: yaml

    node_type: assign
    targets:
      - ctx:
          node_type: store
        id: a
        node_type: name
    value:
      ctx:
        node_type: load
      id: b
      node_type: name

Note that we're representing the AST as a `YAML <http://en.wikipedia.org/wiki/yaml>`_ document, which
provides good readability.

Basic Matching
--------------

As you can see, the AST consists of a node with `node_type = assign`, which contains various
subnodes such as a `value` and one or several `targets`. Now, let's assume we want to match all
assignments that contain a variable named `a` in their `targets` list. The `Cody` query for this 
is as follow:

.. code-block:: yaml

    node_type: assign
    targets:
      $contains : {node_type : name, id: a}

Here, we specify that we're looking for a node with `node_type = assign`, which also contains
a node of `node_type = name` and `id = a` somewhere in its `targets` list. To specify the latter
condition, we made use of the :ref:`$contains<contains>` operator, which will match if
one or more nodes within a list match the given description. Special operators are very useful
for advanced pattern matching, you can read more about them in the :doc:`operators <operators>`
documentation.

References
----------

Often when looking for certain code patterns, we want to store a part of a matched tree and reuse it
somewhere else in our pattern. This is akin to using a parens operator in Regex, like 
`/(foo) is \1/', which will match `foo is foo`. In `Cody`, the operators we use for this are called
`$store<store>` and `$ref<ref>`, and they work as follows:

.. code-block:: yaml

  node_type: for
  target :
    $store : 