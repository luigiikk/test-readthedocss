Existing Tests
================
This smell occurs when developers add new assertions to an existing test instead of writing a dedicated test case for a different behavior.

Example:

.. code-block:: javascript

  test("User login succeeds", () => {
    const user = login();
    expect(user.logged).toBe(true);
    expect(user.role).toBe("admin"); // Unrelated behavior added here
  });

Refactor:

.. code-block:: javascript

  test("User login succeeds", () => {
    const user = login();
    expect(user.logged).toBe(true);
  });

  test("Default user role is admin", () => {
    const user = login();
    expect(user.role).toBe("admin");
  });

.. note::
  Each test should verify one focused behavior to improve test isolation.