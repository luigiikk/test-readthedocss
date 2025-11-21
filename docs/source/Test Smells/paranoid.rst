Paranoid
===============
This test smell occurs when a test (and as a result, its subject) covers edge cases that are not actually reachable in production, making the test unrealistic and possibly giving false confidence. 

Example:

.. code-block:: javascript

  test("should handle negative infinity value", () => {
    expect(service.process(-Infinity)).toBeDefined();
  });

Refactor:

.. code-block:: javascript

  test("should handle null input gracefully", () => {
    expect(() => service.process(null)).toThrow(Error);
  });

.. note::
  Focus tests on realistic inputs and behaviours that actually occur in production.