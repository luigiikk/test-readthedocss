Test Run War
===============
This type of smell occurs when multiple developers run the test suite simultaneously and failures happen randomly (race condition, shared resources).

Example:

.. code-block:: javascript

  test("create user in shared DB", () => {
    db.insert("user");
    expect(db.count()).toBe(1); // Flaky if multiple executions happen
  });

Refactor:

.. code-block:: javascript

  // Use isolated test data / mock DB instead
  const mockDb = createMockDb();

  test("create user safely", () => {
    mockDb.insert("user");
    expect(mockDb.count()).toBe(1);
  });

.. note::
  Shared mutable state creates instability.