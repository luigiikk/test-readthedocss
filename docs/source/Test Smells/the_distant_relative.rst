The Distant Relative
=======================
This test smell occurs when a test belongs to a module but asserts the behavior of a dependency rather than the unit under test. It validates something "external" instead of the intended scope.

Example:

.. code-block:: javascript

  test("User login initializes database", () => {
    const db = new Database();
    login("john", "123");
    expect(db.isConnected()).toBe(true); 
  });

Refactor:

.. code-block:: javascript

  test("Login returns success", () => {
    const result = login("john", "123");
    expect(result).toBe(true);
  });

.. note::
  The test should validate only the behavior of the intended unit, not its dependencies.