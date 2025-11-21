Chain Gang
===============
This type of test smell occurs when two or more tests must run in a specific order due to shared state or execution dependencies.

Example:

.. code-block:: javascript

  let counter = 0;

  test("increment counter", () => {
    counter++;
    expect(counter).toBe(1);
  });

  test("validate counter", () => {
    expect(counter).toBe(1); // Depends on previous test
  });

Refactor:

.. code-block:: javascript

  test("increment counter and validate", () => {
    let counter = 0;
    counter++;
    expect(counter).toBe(1);
  });

.. note::
  Each test must be fully independent, with its own setup.