Mock Everything
==================
This type of test smell occurs when all parts of the test are mocked, so the test verifies nothing meaningful about real behaviour or integration.
Example:

.. code-block:: javascript

  const userService = mock(UserService);
  userService.getById = jest.fn().mockReturnValue({ id:1, name:"X" });

  test("do something", () => {
    expect(userService.getById(1)).toBe({ id:1, name:"X" });
  });

Refactor:

.. code-block:: javascript

  test("getById returns expected user", () => {
    const service = new UserService(realRepository);
    expect(service.getById(1)).toEqual({ id:1, name:"X" });
  });

.. note::
  Use mocks sparingly. Over-mocking can mean tests don’t validate real system behaviour.