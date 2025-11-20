Interactive Test
=================
This test smell occurs when user input or manual interaction is required during test execution, preventing full automation.

Example:

.. code-block:: javascript

  test("Login requires user input", () => {
    const email = prompt("Enter email");
    expect(login(email)).toBe(true);
  });

Refactor:

.. code-block:: javascript

  test("Login succeeds with valid credentials", () => {
    expect(login("john@example.com")).toBe(true);
  });

.. note::
  Automated tests must not depend on UI input or developer manual action.