Data Sensitivity
===================
This smell occurs when tests depend on changing external data (such as a mutable database), which can cause inconsistent test results.

Example:

.. code-block:: javascript

  test("should find 10 users", () => {
    const users = db.getAllUsers();
    expect(users.length).toBe(10); // Fails if DB changed
  });

Refactor:

.. code-block:: javascript

  beforeEach(() => {
    db.seed(testUsers);
  });

  test("should find seeded users", () => {
    const users = db.getAllUsers();
    expect(users.length).toBe(testUsers.length);
  });

.. note::
  Always control test data state (fixtures, mocks, seeding).