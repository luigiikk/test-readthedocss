Indecisive
==========
This test smell occurs when a test contains branching logic (such as if/else inside the test) or conditional assertions, making the test behaviour unclear and hard to predict. 


Example:

.. code-block:: javascript

  test("process value", () => {
    const result = process(value);
    if (value > 10) {
      expect(result).toBeGreaterThan(10);
    } else {
      expect(result).toBeLessThanOrEqual(10);
    }
  });

Refactor:

.. code-block:: javascript

  test("process value greater than 10", () => {
    expect(process(20)).toBeGreaterThan(10);
  });

  test("process value less or equal 10", () => {
    expect(process(5)).toBeLessThanOrEqual(10);
  });

.. note::
  Remove conditional logic from tests so each test has a clear and deterministic expectation.