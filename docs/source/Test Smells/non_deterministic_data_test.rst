Non-deterministic Data Test
============================

This type of test smell occurs when a test case depends on random data or non-deterministic elements, such as random functions.

Example:

.. code-block:: javascript

  it('should generate a random user ID', () => {
  const userId = generateRandomUserId();
  expect(userId).toHaveLength(10);
  });

Refactor:


.. note::
  Tests that rely on non-deterministic data may produce inconsistent results, making it harder to maintain reliable tests. It is recommended to replace random data with fixed or mocked data to ensure test reliability.