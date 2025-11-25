Time Bomb Data
=================
This test smell occurs when tests use hard-coded or poorly chosen dates/times, which may produce correct results today but will fail tomorrow, as dates shift, time zones change, or edge date conditions arise. 


Example:

.. code-block:: javascript

  test("should expire license", () => {
    const now = new Date("2022-12-31T23:59:59Z");
    expect(license.isExpired(now)).toBe(true);
  });

Refactor:

.. code-block:: javascript

  test("should expire license after period", () => {
    const start = new Date();
    const expirationDate = new Date(start.getTime() + licencePeriodInMs);
    expect(license.isExpired(expirationDate)).toBe(true);
  });

.. note::
  Avoid relying on fixed calendar dates; either mock time or derive dates relative to “now” so tests remain valid over time.