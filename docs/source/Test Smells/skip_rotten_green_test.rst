Skip Rotten Green Test
======================
This smell occurs when tests include guards (conditional returns, early exits, skips) that prevent execution of some assertions under certain conditions, allowing the test to pass without verifying the intended behavior.

Example:

.. note::
  Avoid early exits in tests that bypass assertions. Use framework-supported skipping/assumptions instead of manual guards.