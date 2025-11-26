Broad Assertion
=================
This test smell occurs when assertions are too broad or imprecise — for example using generic checks rather than exact comparisons, making failures harder to diagnose.
Example:

.. code-block:: javascript

  test("should get user", () => {
    const user = service.getUser(1);
    expect(user).toBeTruthy(); // broad assertion
  });

Refactor:

.. code-block:: javascript

  test("should get user with correct properties", () => {
    const user = service.getUser(1);
    expect(user.id).toBe(1);
    expect(user.name).toBe("Alice");
  });

.. note::
  Use precise, targeted assertions so test failures clearly point to the root cause.  