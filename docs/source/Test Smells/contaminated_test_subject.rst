Contaminated Test Subject
==========================
This smell occurs when the system under test is configured in unrealistic ways to make testing easier, causing misleading results.

Example:

.. code-block:: javascript

  const service = new PaymentService();
  service.disableSecurity(); // Not realistic!

  test("should accept payment", () => {
    expect(service.pay()).toBe(true);
  });

Refactor:

.. code-block::javascript

  const secureService = new PaymentService();

  test("should validate secure payment", () => {
    expect(secureService.pay()).toBe(true);
  });

.. note::
  The SUT must behave as in real usage.