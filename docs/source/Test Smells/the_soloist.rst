The Soloist
==============
This test smell occurs when a test can only run successfully when no other tests are running (because it relies on exclusive resources, global state, or order) — making suite execution brittle and non-parallelizable. 

.. note::
  Tests should not assume exclusivity of shared resources or depend on being the only test running.