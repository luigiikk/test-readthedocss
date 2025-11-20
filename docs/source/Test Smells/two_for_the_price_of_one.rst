Two for the Price of One
=========================
This test smell occurs when a single test case verifies multiple different behaviors or use cases at once using the same setup. When one assertion fails, other issues may remain unnoticed, reducing fault isolation and making debugging more difficult.

Example:

.. code-block:: javascript

  test("User profile validations", () => {
  const user = new User("John", "john@example.com
  ");

  expect(user.getName()).toBe("John");
  expect(user.isEmailValid()).toBe(true);


  });

Refactor:

.. code-block:: javascript

  test("Returns correct username", () => {
  const user = new User("John", "john@example.com
  ");
  expect(user.getName()).toBe("John");
  });

  test("Validates email format", () => {
  const user = new User("John", "john@example.com
  ");
  expect(user.isEmailValid()).toBe(true);
  });

.. note::
  Separate each behavior into its own test to improve readability and fault localization.

  Hard Coded Test Data

  This test smell occurs when input values and expected results are hard-coded inside test methods, making it harder to understand the relationship between test inputs and outcomes. Modifying the system under test often requires changes to multiple tests.
