Assertion Chorus Test
========================
This type of test smell occurs when a single test includes a long sequence of assertions to check various outcomes. While sometimes necessary, too many assertions in one test can reduce clarity and make it harder to identify which condition failed.
.. code-block:: javascript


Refactor:


.. note::
  Consider splitting the test into smaller, focused tests or grouping related assertions to improve readability and make debugging easier when a test fails.

