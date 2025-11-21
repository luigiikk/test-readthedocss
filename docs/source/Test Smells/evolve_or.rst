Evolve Or
=============
This smell occurs when tests continue to pass even after the system changes because they were not updated accordingly (false positives).

Example:

.. code-block:: javascript

  // Code now uses discount but test still checks old behavior
  test("price test", () => {
    const result = calculatePrice(100);
    expect(result).toBe(100); // Should be 90 now!
  });

Refactor:

.. code-block:: javascript

  test("price with discount", () => {
    const result = calculatePrice(100);
    expect(result).toBe(90);
  });

.. note::
  Test evolution must follow system evolution.