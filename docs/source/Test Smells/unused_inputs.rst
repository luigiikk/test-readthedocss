Unused Inputs
===============
This test smell occurs when inputs controlled by the test suite are never actually used by the code under test. 


Example:

.. code-block:: javascript

  test("create user", () => {
    const name = "John";
    const age = 30; // never sent/used
    const user = new User(name);
    expect(user.name).toBe("John");
    });

Refactor:

.. code-block:: javascript

  test("create user with name", () => {
    const name = "John";
    const user = new User(name);
    expect(user.name).toBe("John");
  });

.. note::
  Ensure that all inputs provided by the test are relevant and exercised by the code under test.