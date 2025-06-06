Duplicate Assert
==================
This type of test smell occurs when the test case contains more than one assertion statement with the same parameters or validating the same condition. These redundant assertions provide no additional value and can unnecessarily bloat the test.

Example:

.. code-block:: javascript

  test("should return the correct username", () => {
    const user = new User("Jhon", 30);
    expect(user.name).toBe("Jhon");
    expect(user.name).toBe("Jhon"); 
  });

Refactor:


.. note::
  Remove duplicate assertions that verify the same condition. Keep your tests concise and focused to improve readability and reduce unnecessary repetition.