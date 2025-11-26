Bury The Lede
================
This test smell occurs when a test’s setup is so onerous or verbose that by the time the reader reaches the actual invocation of the subject and its assertion, the purpose of the test is forgotten. 

Example:

.. code-block:: javascript

  beforeEach(() => {
    // dozens of lines setting up multiple services, mocks, databases, file writes, etc.
    serviceA.start();
    serviceB.configure();
    db.seedLargeDataset();
    // many other steps…
  });

  test("should update user profile", () => {
    const result = userService.updateProfile(userId, newProfile);
    expect(result.success).toBe(true);
  });

Refactor:

.. code-block:: javascript

  beforeEach(() => {
    minimalSetupForUserService();
  });

  test("should update user profile", () => {
    const result = userService.updateProfile(userId, newProfile);
    expect(result.success).toBe(true);
  });

.. note::
  Keep test setup light and focused; the invocation and assertion should be immediately visible and understandable without wading through large setup blocks.