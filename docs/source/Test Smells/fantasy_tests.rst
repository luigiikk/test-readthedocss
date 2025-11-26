Fantasy Tests
================
This test smell occurs when tests pass under unrealistic or oversimplified conditions (e.g., mocks/stubs return trivial data), making them irrelevant for production behaviour and giving false confidence.
Example:

.. code-block:: javascript

  mockApi.getUser = () => ({ id:1, name:"Test" });
    test("should send welcome email", () => {
      expect(emailService.sendWelcome(1)).toBe(true);
    });

Refactor:

.. code-block:: javascript

  test("should send welcome email with real user data", async () => {
    const realUser = await dbUser.create({ name:"Alice" });
    expect(emailService.sendWelcome(realUser.id)).toBe(true);
  });

.. note::
Tests should align with realistic scenarios — mocks/stubs should reflect real behaviour not idealised fantasy.