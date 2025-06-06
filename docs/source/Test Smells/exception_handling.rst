Exception Handling
========================
This type of test smell occurs when a test case uses the try-catch method, i.e., manually handles exceptions. This practice can obscure test intent and make the code more verbose and harder to read. Modern testing frameworks provide clearer and more concise ways to assert thrown errors.

Example:

.. code-block:: javascript

  test("should throw an error when the user is not found", () => {
    try {
      findUserById(999);
    } catch (error) {
      expect(error.message).toBe("User not found");
    }
  });
Refactor:

.. note::
   Avoid using try-catch blocks in tests to assert exceptions. Instead, use built-in matchers like toThrow for better readability and clarity.
