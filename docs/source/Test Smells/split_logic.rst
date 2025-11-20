Split Logic
============
This test smell occurs when a single logical validation is fragmented across multiple test cases, forcing the developer to mentally assemble the full behavior.

Example:

.. code-block:: javascript

  test("Initial state", () => {
    expect(getStatus()).toBe("pending");
  });

  test("After update", () => {
    update();
    expect(getStatus()).toBe("approved");
  });

Refactor:

.. code-block:: javascript

  test("Status transitions from pending to approved", () => {
    expect(getStatus()).toBe("pending");
    update();
    expect(getStatus()).toBe("approved");
  });

.. note::
  Keep related behavior in the same test for clarity.