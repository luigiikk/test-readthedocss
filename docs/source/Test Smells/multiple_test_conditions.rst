Multiple Test Conditions
=========================
This test smell occurs when a test attempts to apply the same test logic to many sets of input values each with their own corresponding expected result, often reducing clarity of what the specific test case is verifying. 

Example:

.. code-block:: javascript

  const cases = [
  { in: 1, out: 2 },
  { in: 2, out: 4 },
  { in: 3, out: 6 }
  ];
  test("multiple inputs", () => {
    cases.forEach(c => {
      expect(double(c.in)).toBe(c.out);
    });
  });

Refactor:

.. code-block:: javascript

  test("double of 1 is 2", () => {
    expect(double(1)).toBe(2);
  });
  test("double of 2 is 4", () => {
    expect(double(2)).toBe(4);
  });
  test("double of 3 is 6", () => {
    expect(double(3)).toBe(6);
  });

.. note::
  Breaking out each condition into its own named test improves readability and diagnosability of failures.