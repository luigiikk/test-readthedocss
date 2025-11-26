Noisy Setup
=============
This test smell occurs when a verbose sequence of low-level setup steps is executed for each test, making the test hard to read and understand what is being tested.
Example:

.. code-block:: javascript

  beforeEach(() => {
    db.connect();
    db.createTable("users");
    db.insert({id:1,name:"Alice"});
    db.insert({id:2,name:"Bob"});
    network.mockEndpoint("/users");
    fileSystem.createFile("config.json");
  });

  test("should fetch user by id", async () => {
    const user = await userService.fetchById(1);
    expect(user.name).toBe("Alice");
  });

Refactor:

.. code-block:: javascript

  beforeEach(() => {
    minimalUserFixture();
  });

  test("should fetch user by id", async () => {
    const user = await userService.fetchById(1);
    expect(user.name).toBe("Alice");
  });

.. note::
  Setup should be minimal and clearly relevant to the test being executed.