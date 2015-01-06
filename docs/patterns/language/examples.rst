========
Examples
========

An example is worth a thousand lines of documentation ;)

Python
======

The following patterns are Python-specific.

Unconditional exception without action
--------------------------------------

Catches a `try/except` block that does neither specify an exception type, nor
perform any operation in the `except` block.

.. code-block:: yaml

  handlers:
    body: {node_type: pass}
    type: null
  node_type: tryexcept

This catches e.g. the following code:

.. code-block:: python

  try:
    #...
  except:
    pass

Use of `has_key`
----------------

Catches a call to a `has_key` function, which is an attribute of an object.

.. code-block:: yaml

  func: {attr: has_key, node_type: attribute}
  node_type: call

This catches e.g. the following code:

.. code-block:: python

  d = {'a' : 1,'b' : 2}
  d.has_key('a')

Use of `map` instead of list comprehension
------------------------------------------

Catches a call to a function called `map`.

.. code-block:: yaml

  func:
    ctx: {node_type: load}
    id: map
    node_type: name
  node_type: call

.. code-block:: python

  items = ["foo","bar","baz"]
  mapped_items = map(lambda x: len(x),items)


Not making use of the `.items()` method
---------------------------------------

Catches a `for` loop that iterates over the keys of a dictionary-like object and retrieves
the value of each item within the loop, instead of using the `.items()` function.

Here, we make use of the `match_first` special option, which ensures that we first visit the
`iter` and `target` attributes of the `for` loop, where we populate the `target` and `d`
variables, which we then use within the `body` of the for loop.

.. code-block:: yaml

  node_type: for
  $ : {match_first: [iter, target]}
  body:
    $anywhere:
      node_type: subscript
      ctx: {node_type: load}
      slice:
        node_type: index
        value:
          id:
            $ref: {name: target.id}
          node_type: name
      value:
        id:
          $ref: {name: d.id}
        node_type: name
  iter:
    name: d
    $store:
      node_type: name
  target:
    name: target
    $store:
      node_type: name

This catches e.g. the following code:

.. code-block:: python

  d = {'a' : 1,'b' :2,'c' : 3}
  for key in d:
      value = d[key]
