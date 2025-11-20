Long Function or Long Method
============================
This test smell occurs when tests contain too many steps and assertions, making them hard to interpret and trace when failures occur.

Example:

.. code-block:: javascript

  test("Full user onboarding", () => {
    const user = registerUser();
    expect(user).toBeDefined();
    loginUser(user);
    expect(isLoggedIn()).toBe(true);
    completeProfile(user);
    expect(isProfileComplete()).toBe(true);
    subscribePlan(user);
    expect(hasSubscription()).toBe(true);
  });

Refactor:

.. code-block:: javascript

  test("User registration works", () => {
    const user = registerUser();
    expect(user).toBeDefined();
  });

  test("User can login", () => {
  // ...
  });


.. note::
  Shorter tests are easier to debug and align better with single-assert best practices.