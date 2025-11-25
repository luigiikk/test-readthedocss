Generous Leftovers
==================
This test smell occurs when a test case creates data or state that is persisted or reused by another test, causing inter-test dependencies and hidden coupling. 

Example:

.. code-block:: javascript

  test("create user", () => {
    database.insert({ id: 1, name: "Alice" });
    expect(database.exists(1)).toBe(true);
  });

  test("user login uses existing data", () => {
    expect(login(1)).toBe(true); // depends on user created by previous test
  });

Refactor:

.. code-block:: javascript

  beforeEach(() => {
    database.clear();
    database.insert({ id: 1, name: "Alice" });
  });

  test("create user and login", () => {
    expect(login(1)).toBe(true);
  });

.. note::
  Ensure each test runs in an isolated context without relying on leftover state from other tests.