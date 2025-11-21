Generative
=============
This type of test smell occurs when a test loops over a data structure of discrete inputs and expected outputs to generate test cases, thereby reducing clarity of each specific case and making failures harder to interpret. 
Catálogo de Test Smells

Example:

.. code-block:: javascript

  const cases = [
  { input: 1, expected: 2 },
  { input: 2, expected: 4 },
  { input: 3, expected: 6 },
  ];

  cases.forEach(c => {
    test(input ${c.input}, () => {
      expect(service.double(c.input)).toBe(c.expected);
    });
  });

Refactor:

.. code-block:: javascript

  test("double of 1 is 2", () => {
    expect(service.double(1)).toBe(2);
  });

  test("double of 2 is 4", () => {
    expect(service.double(2)).toBe(4);
  });

  test("double of 3 is 6", () => {
    expect(service.double(3)).toBe(6);
  });

.. note::
  While parameterised testing can be useful, ensure each case remains clear and failures easy to diagnose.