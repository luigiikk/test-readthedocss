Assertion Loop
================

This type of test smell occurs when a test case creates an assertion in the loop.

Example:

.. code-block:: javascript

  test("should return all users with valid names", () => {
  const users = getUsers();

  for (let user of users) {
  expect(user.name).toBeDefined();
  }
  });

Refactor:

.. note::
  Having assertions in a loop can make it harder to diagnose which iteration caused the failure. Refactoring the loop to a single assertion improves the readability and maintainability of the test.