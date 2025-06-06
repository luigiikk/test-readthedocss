Empty Test
============
This type of test smell occurs when the test case does not contain a single executable statement. Empty tests add noise to the test suite, create a false sense of completeness, and may indicate forgotten or unfinished implementations.

Example:

.. code-block:: javascript

  test("should update user name", () => {
    // test not implemented
  });

Refactor:

.. note::
  Avoid leaving empty test blocks in the codebase. Either implement the test or remove the placeholder to keep the suite clean and meaningful.