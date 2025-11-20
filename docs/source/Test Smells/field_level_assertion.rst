Field-Level Assertion
=====================
This test smell occurs when every internal field of an entity is validated individually, instead of testing the behavior or using a higher-level assertion.

Example:

.. code-block:: javascript

    const user = createUser();

    expect(user.name).toBe("John");
    expect(user.email).toBe("john@example.com");
    expect(user.role).toBe("admin");

Refactor:

.. code-block:: javascript

  test("Creates user with correct data", () => {
    const user = createUser();
    expect(user).toMatchObject({ role: "admin" });
  });

.. note::
  Validate meaningful behavior, not every internal detail.