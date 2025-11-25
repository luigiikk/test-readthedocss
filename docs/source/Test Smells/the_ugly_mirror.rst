The Ugly Mirror
=================
This test smell occurs when a test case mirrors the implementation code under test exactly—essentially reproducing the logic rather than verifying behaviour.
Example:

.. code-block:: javascript

  function sum(a, b) { return a + b; }

  test("sum should add", () => {
    const result = a + b; // same logic as production
    expect(sum(a,b)).toBe(result);
  });

Refactor:

.. code-block:: javascript

  test("sum returns correct result", () => {
    expect(sum(2, 3)).toBe(5);
  });

.. note::
  Tests should rely on observable outcomes, not replicate production logic inside them.