Return in Test
===============

This type of test smell occurs when a test case that return something


Example:

.. code-block:: javascript

  test("should return a user", () => {
  const user = getUser();
  return user;
  });

.. note::
  Tests should not return values as they are primarily meant for assertions and verification, not for returning data. Returning values can indicate improper test structure or misunderstanding of test case usage.
