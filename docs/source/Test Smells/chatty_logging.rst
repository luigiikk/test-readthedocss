Chatty Logging
=================
This smell occurs when the test logs excessively to describe behavior, instead of relying on expressive assertions or clear test names.

Example:

.. code-block:: javascript

  test("Check balance", () => {
    console.log("Requesting balance...");
    const balance = getBalance();
    console.log("Balance is: " + balance);
    expect(balance).toBeGreaterThan(0);
  });

Refactor:

.. code-block:: javascript

  test("Balance should be greater than zero", () => {
    expect(getBalance()).toBeGreaterThan(0);
  });

.. note::
  Assertions and test naming should communicate intent — not console logs.