Inefficient Waits
====================
This type of test smell occurs when hard-coded delays are added to force the test to pause for a specific time (e.g., sleep), making the execution inefficient and unstable.

Example:

.. code-block:: javascript

  test("should load data", async () => {
    await new Promise(resolve => setTimeout(resolve, 5000)); // Hard wait
    const result = await loadData();
    expect(result).toBeDefined();
  });

Refactor:

.. code-block:: javascript

  test("should load data", async () => {
    const result = await loadData();
    expect(result).toBeDefined();
  });

.. note::
  Instead of adding delays, tests should wait for actual conditions or promises to resolve.