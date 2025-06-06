Magic Number Test
===================
This type of smell occurs when assertions contain numeric literals (magic numbers) directly in the code. Using unexplained numbers reduces readability and makes it harder to understand the intent behind the test.

Example:

.. code-block:: javascript

  test("should check if user is adult", () => {
    const user = new User("John", 25);
    expect(user.age >= 18).toBe(true);
  });


.. note::
  Replace magic numbers with named constants to improve clarity, express intent, and facilitate future changes.