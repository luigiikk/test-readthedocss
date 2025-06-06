Assertion Roulette
====================

This type of test smell occurs when a test case contains too many assertions without clear explanations.

Example:

.. code-block:: javascript

  test("should validate user data", () => {
    const user = getUser();
    expect(user.name).toBe("Jhon"); 
    expect(user.age).toBe(25);
    expect(user.email).toBe("jhondoe@email.com"); 
  });

Refactor:

.. note::
  Grouping many assertions without clear purposes in a single test hinders readability and debugging. Consider breaking the test into multiple smaller tests, each focusing on a specific behavior or property.