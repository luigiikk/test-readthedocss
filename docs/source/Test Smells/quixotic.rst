Quixotic
==============
This test smell occurs when a test charts an idealistic path through the subject code, cherry-picking inputs that provide minimum resistance (e.g., in test data setup) and thereby missing coverage of negative/complex cases. 
test-smell-catalog.readthedocs.io

Example:

.. code-block:: javascript

  test("all happy flows pass", () => {
    expect(service.execute(validInput)).toBe("OK");
  });

Refactor:

.. code-block:: javascript

  test("happy flow executes", () => {
    expect(service.execute(validInput)).toBe("OK");
  });

  test("invalid input triggers error", () => {
    expect(() => service.execute(invalidInput)).toThrow(Error);
  });

.. note::
  Avoid only testing the “ideal” path—include negative and boundary conditions too.