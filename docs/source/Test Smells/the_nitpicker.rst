The Nitpicker
=================

This test smell occurs when a unit test compares a complete output when it’s really only interested in a small part of it — making the test more fragile and tightly coupled to implementation details. 


.. note::
  Focus on the behaviour you care about — not the full implementation details. Comparing full large outputs locks you into fragile tests that break whenever minor formatting changes occur.