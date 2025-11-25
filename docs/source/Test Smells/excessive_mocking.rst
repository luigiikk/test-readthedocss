Excessive Mocking
==================
This test smell occurs when a test case requires many mocks just to run, making the test heavy, brittle, and focused on interactions rather than outcomes.
Example:


.. note::
  A large number of mocks often signals design issues in subject under test and makes test maintenance harder.