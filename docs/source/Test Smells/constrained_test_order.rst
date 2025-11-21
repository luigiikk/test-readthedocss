Constrained Test Order
========================
This test smell happens when tests only pass when executed in a specific sequence, or when they depend on values left behind by others.

Example:

.. code-block:: javascript

  test("A", () => {
    global.value = 10;
    expect(global.value).toBe(10);
  });

  test("B", () => {
    expect(global.value).toBe(10); // Breaks if executed alone
  });

Refactor:

.. code-block:: javascript

  beforeEach(() => {
    global.value = 10;
  });

  test("B", () => {
    expect(global.value).toBe(10);
  });

.. note::
  Test ordering must never influence the result.