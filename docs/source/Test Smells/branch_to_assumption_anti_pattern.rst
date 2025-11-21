Branch To Assumption Anti-Pattern
===================================
This smell happens when assumptions are conditionally executed, causing incorrect handling of invalid test conditions.

Example:

.. code-block:: javascript

  test("works only if condition", () => {
    if (userExists) {
      expect(true).toBe(true);
    }
  });

Refactor:

.. code-block:: javascript

  test("should ensure valid precondition", () => {
    expect(userExists).toBe(true);
  });

.. note::
  Preconditions should be checked explicitly, not silently skipped.