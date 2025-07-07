Duplicate Statements Test
==================
This type of test smell occurs when a duplicate sequence of statements appears within the statement block of one or multiple behavioral entities (functions, test cases, etc.). This repetition increases code clutter and makes the test suite harder to maintain or refactor.

Example:

Refactor:


.. note::
  Move the repeated logic into a helper function or setup block. This improves readability, avoids redundancy, and ensures consistency across your tests.

