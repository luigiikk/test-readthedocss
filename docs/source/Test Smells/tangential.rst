Tangential
=============
This test smell occurs when the test or its subject claim to target a certain functionality, but the bulk of complexity and verification is aimed at some subordinate or different responsibility — the test is tangential to what it purports to test. 


Example:

.. code-block:: javascript

  test("should calculate order total", () => {
    const order = new Order(items);
    // The test spends most of its effort verifying tax-calculation logic from an imported utility
    expect(taxUtil.computeTax(items)).toBe(5);
    expect(order.total()).toBe(105);
  });

Refactor:

.. code-block:: javascript

  test("order total includes tax", () => {
    const order = new Order(items);
    expect(order.total()).toBe(105);
  });

  test("tax utility computes correctly", () => {
    expect(taxUtil.computeTax(items)).toBe(5);
  });

.. note::
  Each test should focus clearly on the behaviour of the subject under test, not drift into verifying supporting utilities or unrelated responsibilities.