Army of Clones Test
========================
This type of test smell occurs when different tests perform and implement similar actions, leading to duplicated pieces of test code. Duplication increases maintenance effort and makes it harder to apply changes consistently across all tests.Example:

.. code-block:: javascript


Refactor:


.. note::
  To improve maintainability and reduce duplication, extract common setup or logic into helper functions or use test parameterization when possible.