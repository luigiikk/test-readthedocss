Share The World
================
This type of test smell occurs when a test sets up all its resources at the start of the fixture (shared for many tests), leading to either bleeding of state between tests or extra work to keep the shared setup tidy.


.. note::
  Shared large fixtures bring risk of cross-test interactions and hidden dependencies — isolate setup per area.