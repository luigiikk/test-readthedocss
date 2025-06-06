Ignored Test
========================
This type of test smell occurs when a test case uses functions that skip tests (e.g., it.skip, test.skip). Skipped tests may indicate unfinished or obsolete code and can lead to a false sense of test coverage, reducing confidence in the test suite.

Example:

.. code-block:: javascript

  it.skip('should correctly sum two numbers', () => {
    const result = sum(2, 3);
    expect(result).toBe(5);
  });

Refactor:

.. note::
   Avoid skipping tests without proper documentation. If a test is not needed, remove it. Otherwise, ensure it is re-enabled or clearly marked with a reason for being skipped.
