Conditional Test Logic
========================
This type of test smell occurs when a test case contains conditional instructions.

Example:

.. code-block:: javascript

  test("should validate user role", () => {
    const user = getUser();

    if (user.role === "admin") {
      expect(user.hasAccess).toBe(true);
    } else {
      expect(user.hasAccess).toBe(false);
    }
  });
Refactor:

.. note::
   Conditional logic in test cases should be avoided. Instead, split the test into separate, clearly defined cases to improve readability and ensure predictable outcomes.