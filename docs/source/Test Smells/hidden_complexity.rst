Hidden Complexity
===================
This test smell occurs when a seemingly harmless API used by a test actually hides heavy computation or complex logic behind the scenes, making tests slow and unpredictable.

Example:

.. code-block:: javascript

  test("Generate user statistics", () => {
    const stats = generateUserStatistics();
    expect(stats.total).toBeGreaterThan(0);
  });

Refactor:

.. code-block:: javascript

  test("Generate user statistics", () => {
    const mockUsers = [{ active: true }];
    const stats = calculateStatistics(mockUsers);
    expect(stats.total).toBe(1);
  });

.. note::
  Prefer lightweight helper functions or mocked data over expensive operations.