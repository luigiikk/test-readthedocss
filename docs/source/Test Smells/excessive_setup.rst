Excessive Setup
================
This test smell occurs when many dependencies must be created beforehand (classes, OS dependencies, database, etc), causing the test to lose focus from its goal. 


Example:

.. code-block:: javascript

  beforeEach(async () => {
    await os.configureNetwork();
    await db.initializeSchema();
    await populateHugeDataset();
    await startMessagingSystem();
  });

  test("should perform simple calculation", () => {
    expect(calcService.compute(5)).toBe(25);
  });

Refactor:

.. code-block:: javascript

  beforeEach(() => {
    initMinimalDependencies();
  });

  test("should perform simple calculation", () => {
    expect(calcService.compute(5)).toBe(25);
  });

.. note::
  Keep setup minimal and directly relevant to the behaviour being tested.