Layer Testing
================
This test smell occurs when tests depend on multiple layers of functionality rather than isolating the unit under test—there may be many indirect calls and dependencies, making tests fragile and slower. 


Example:

.. code-block:: javascript

  test("should send email after order", () => {
    orderService.placeOrder(item);
    paymentService.processPayment();
    shippingService.ship(order);
    emailService.sendConfirmation(order);
    assertTrue(emailInbox.received(order.id));
  });

Refactor:

.. code-block:: javascript

  test("should send confirmation email for order", () => {
    const order = mockOrder();
    emailService.sendConfirmation(order);
    assertTrue(emailInbox.received(order.id));
  });

.. note::
  Focus on one layer—the unit under test. Avoid chaining through many layers in a single test, which increases complexity and coupling.