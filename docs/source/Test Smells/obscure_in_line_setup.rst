Obscure In-Line Setup
======================
This test smell occurs when the setup required for the test is performed directly inside the test method and is complex, making the test long and difficult to follow.
Example:

.. code-block:: javascript

  test("should calculate discount after many steps", () => {
    const user = new User();
    user.setAge(30);
    user.setMembership("premium");
    user.addPurchase({ amount:100 });
    user.addPurchase({ amount:200 });
    const date = new Date("2025-12-01");
    user.setJoinDate(date);
    const discount = discountService.calculate(user);
    expect(discount).toBe(50);
  });

Refactor:

.. code-block:: javascript

  function buildPremiumUser() {
    const user = new User();
    user.setAge(30);
    user.setMembership("premium");
    user.addPurchases([100,200]);
    return user;
  }

  test("should calculate discount for premium user", () => {
    const user = buildPremiumUser();
    const discount = discountService.calculate(user);
    expect(discount).toBe(50);
  });

.. note::
  Move complex setup into helper methods or fixtures so the test becomes shorter and its purpose immediately apparent.