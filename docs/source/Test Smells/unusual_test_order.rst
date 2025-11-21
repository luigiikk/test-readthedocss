Unusual Test Order
===================
This test smell occurs when unit tests explicitly call each other.

Example:

.. code-block:: javascript

  test("A", () => {
    expect(1).toBe(1);
  });

  test("B", () => {
    test("A"); // Wrong usage
  });

Refactor:

.. code-block:: javascript

  test("A", () => {
    expect(1).toBe(1);
  });

.. note::
  Tests must not invoke other test cases.