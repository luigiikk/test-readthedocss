Magic Values
================
This test smell occurs when literal values are used directly in assertions or parameters without explanation. Such values make tests less expressive and harder to update.

Example:

.. code-block:: javascript

  test("Max retry value", () => {
  expect(getRetryLimit()).toBe(3);
  });

Refactor:

.. code-block:: javascript

  const MAX_RETRY_LIMIT = 3;

  test("Max retry value", () => {
  expect(getRetryLimit()).toBe(MAX_RETRY_LIMIT);
  });

.. note::
  Replace literals with named constants to improve readability and intention.