Mistaken Identity
===================
This smell occurs when the name of a test gives a contrary or misleading indication relative to the actual behaviour being tested, causing confusion. 

Example:

.. code-block:: javascript

  test("should fail when user invalid", () => {
    expect(login("validUser", "validPass")).toBe(true);
  });

Refactor:

.. code-block:: javascript

  test("should succeed with valid credentials", () => {
    expect(login("validUser", "validPass")).toBe(true);
  });

.. note::
  Give test names that accurately reflect the behaviour they verify — avoid mismatches between name and logic.