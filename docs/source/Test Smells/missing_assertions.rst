Missing Assertions
====================
This test smell occurs when the subject under test includes behavior which the test does not assert (either implicitly or explicitly), meaning parts of intended behaviour are left unchecked. 


Example:

.. code-block:: javascript

  test("process payment", () => {
    const result = paymentService.process(order);
    // only checks return code but ignores side-effects like inventory decrement
    expect(result).toBe(true);
  });

Refactor:

.. code-block:: javascript

  test("process payment and update inventory", () => {
    const result = paymentService.process(order);
    expect(result).toBe(true);
    expect(inventory.decremented(order.itemId)).toBe(true);
  });

.. note::
  Ensure tests examine all relevant outcomes of behaviour — not just one aspect while ignoring others.