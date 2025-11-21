Dependent Test
===================
This test smell appears when tests rely on the side effects of previously executed tests.

Example:

.. code-block:: javascript

  test("create user", () => {
    db.add("user");
  });

  test("verify user exists", () => {
    expect(db.exists("user")).toBe(true);
  });

Refactor:

.. code-block:: javascript

  test("create and validate user", () => {
    db.add("user");
    expect(db.exists("user")).toBe(true);
  });

.. note::
  Tests must not rely on data created by other tests.