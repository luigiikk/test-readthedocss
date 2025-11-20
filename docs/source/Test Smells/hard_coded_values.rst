Hard-Coded Values
==================
This test smell occurs when expected values or commonly reused configuration values are duplicated across multiple tests instead of being extracted to shared constants or fixtures.

Example:

.. code-block:: javascript

  test("Status should be pending", () => {
    expect(getStatus(0)).toBe("PENDING");
  });

  test("Status should be approved", () => {
    expect(getStatus(1)).toBe("APPROVED");
  });

  Refactor:

.. code-block:: javascript

  const STATUS_PENDING = "PENDING";
  const STATUS_APPROVED = "APPROVED";

  test("Status should be pending", () => {
    expect(getStatus(0)).toBe(STATUS_PENDING);
  });

  test("Status should be approved", () => {
    expect(getStatus(1)).toBe(STATUS_APPROVED);
  });

.. note::
  Centralizing key values minimizes duplication and inconsistencies.