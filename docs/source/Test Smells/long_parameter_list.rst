Long Parameter List
========================
This smell occurs when a test calls a function with a high number of formal parameters (i.e., the test method passes many arguments), making the test brittle and hard to read. 


Example:

.. code-block:: javascript

  test("complex behavior", () => {
    expect(process(a, b, c, d, e, f, g, h, i, j)).toBe(expected);
  });

Refactor:

.. code-block:: javascript

  test("complex behavior simplified", () => {
    const input = { a, b, c, d, e };
    const options = { f, g, h, i, j };
    expect(process(input, options)).toBe(expected);
  });

.. note::
  Reduce parameter count by grouping inputs/outputs or using objects so tests remain clear and maintainable.