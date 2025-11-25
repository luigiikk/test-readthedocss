Code Pollution
===============
This test smell occurs when you modify or add code to the main application solely to facilitate testing (i.e., production code becomes polluted with test-only scaffolding). 
Enterprise Craftsmanship

.. note::
  Do not introduce production code functionality that exists only for tests; keep testing logic in test suite or test helpers.