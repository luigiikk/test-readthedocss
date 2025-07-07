Duplicate Test Code
==================
This type of test smell occurs when multiple tests verify the same behavior or condition, resulting in redundancy. Such duplication adds unnecessary noise to the test suite and can slow down test execution and maintenance.

Example:

Refactor:


.. note::
  Avoid writing multiple tests for the same logic unless you are testing different conditions or contexts. Consolidate redundant tests to keep your test suite clean, focused, and efficient.
