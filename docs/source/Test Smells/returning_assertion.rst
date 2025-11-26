Returning Assertion
======================

This test smell occurs when a test method has an assertion and then returns a value (instead of being void/test only) — mixing test logic and returned values can confuse test frameworks and make results ambiguous. 


.. note::
  Test methods should rely on assertions alone to report success/failure — not return values which are ignored by test frameworks.