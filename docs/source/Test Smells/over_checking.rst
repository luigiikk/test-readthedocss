Over-Checking
===============
This test smell occurs when the test performs assertions that are not relevant to its scope — extraneous assertions distract from the main behaviour and add maintenance overhead. 


Example:

.. code-block:: javascript

  test("user login succeeds", () => {
    const user = service.login("john", "pwd");
    expect(user.id).toBe(5);
    expect(user.name).toBe("John");
    expect(user.age).toBe(30);
    expect(user.address).toEqual({ city:"NY", zip:"10001" }); // unrelated to login
  });

Refactor:

.. code-block:: javascript

  test("user login succeeds", () => {
    const user = service.login("john", "pwd");
    expect(user.id).toBe(5);
    expect(user.name).toBe("John");
  });

.. note::
  Focus assertions on what the test intends to verify — avoid checking unrelated fields which make the test fragile and less meaningful.