Hidden Dependency
==================
This smell happens when tests rely on pre-existing state or resources that are not visible in the test implementation.

Example:

.. code-block:: javascript

  test("should authenticate user", () => {
    expect(auth.login("admin")).toBe(true); // Requires user pre-created!
  });

Refactor:

.. code-block:: javascript

  beforeEach(() => {
    db.addUser({ username: "admin" });
  });

  test("should authenticate user", () => {
    expect(auth.login("admin")).toBe(true);
  });

.. note::
  All dependencies must be explicit within the test setup.