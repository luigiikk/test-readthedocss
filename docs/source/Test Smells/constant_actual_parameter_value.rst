Constant Actual Parameter Value
====================================
This test smell occurs when the actual parameter value passed in test methods is always the same across multiple occurrences, reducing variability and masking issues. 

Example:

.. code-block:: javascript

  test("case 1", () => {
    expect(func(5)).toBe(10);
  });
  test("case 2", () => {
    expect(func(5)).toBe(10);
  });
  test("case 3", () => {
    expect(func(5)).toBe(10);
  });

Refactor:

.. code-block:: javascript

  test("double of 5 is 10", () => {
    expect(func(5)).toBe(10);
  });
  test("double of 7 is 14", () => {
    expect(func(7)).toBe(14);
  });
  test("double of 0 is 0", () => {
    expect(func(0)).toBe(0);
  });

.. note::
  Use different actual parameter values to ensure broader coverage and avoid redundant identical calls.