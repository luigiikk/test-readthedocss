Large Macro Component

This test smell occurs when a macro test component orchestrates too many primitive test operations, reducing comprehensibility and maintainability.

Example:

.. code-block:: javascript

  test("Full checkout flow", () => {
    addItemToCart();
    applyDiscount();
    calculateShipping();
    processPayment();
    confirmOrder();
    sendEmail();
    updateStatus();
    expect(isOrderComplete()).toBe(true);
  });

Refactor:

.. code-block:: javascript

  test("Order completes successfully", () => {
    completeCheckoutFlow();
    expect(isOrderComplete()).toBe(true);
  });

.. note::
  Extract complex behavior into reusable methods or fixtures.