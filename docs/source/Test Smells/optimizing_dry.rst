Optimizing DRY
================
This test smell occurs when the “Don’t Repeat Yourself” principle is over-applied in tests, making them harder to understand due to unnecessary abstractions like helper functions or excessive variables.

Example:

.. code-block:: javascript

  const createUser = () => new User("John", "john@example.com
  ");

  const verifyEmail = (user) => expect(user.isEmailValid()).toBe(true);

  test("Email validation", () => {
    const u = createUser();
    verifyEmail(u);
  });

Refactor:

.. code-block:: javascript

  test("Email validation", () => {
    const user = new User("John", "john@example.com");
    expect(user.isEmailValid()).toBe(true);
  });

.. note::
  Explicitness in tests improves clarity even if some duplication remains.