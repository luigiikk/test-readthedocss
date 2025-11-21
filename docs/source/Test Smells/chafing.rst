Chafing
===========
Occurs when reducing duplication introduces excessive indirection that harms readability.

Example:

.. code-block:: javascript

  const execute = () => sharedSetup() && runTest() && verify();

  test("complex test", () => {
    expect(execute()).toBe(true);
  });

Refactor:

.. code-block:: javascript

  test("simplified test", () => {
    sharedSetup();
    const result = runTest();
    expect(result).toBe(true);
  });

.. note::
  Readability > minimal duplication.