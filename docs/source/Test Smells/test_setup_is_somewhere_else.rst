Test Setup Is Somewhere Else
=================================
This test smell occurs when the test method only does the assertions and/or calls, but the main setup (“given/when”) is hidden somewhere else (in helper methods or external fixtures), making the test harder to read and understand because you must jump elsewhere.
Example:

.. code-block:: javascript

  @BeforeEach
  function heavySetup() {
    prepareDatabase();
    mockServices();
  }

  @Test
  function testUserCreation() {
    assertTrue(userService.create("Alice"));
  }

  // reader must inspect heavySetup() to understand test state

Refactor:

.. code-block:: javascript

  test("should create user successfully", () => {
    const db = new TestDatabase();
    const userService = new UserService(db);
    expect(userService.create("Alice")).toBe(true);
  });

.. note::
  Prefer tests that contain the full arrange-act-assert inside the test or clearly reference a minimal helper with obvious naming so intent is clear.