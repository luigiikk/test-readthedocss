Assert the World
=================
This test smell occurs when a test uses too many assertions unrelated to the main target behavior, producing noise and increasing failure points.

Example:

.. code-block:: javascript

  test("User profile name updates", () => {
    const user = updateName("John");
    expect(user.name).toBe("John");
    expect(user.age).toBe(30);
    expect(user.email).toBe("john@example.com");
    expect(user.active).toBe(true);
  });

Refactor:

.. code-block:: javascript

  test("User profile name updates", () => {
    const user = updateName("John");
    expect(user.name).toBe("John");
  });

.. note::
  Assertions should focus on the behavior that matters for the test objective.