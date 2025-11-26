Assertion Diversion
=====================
This test smell occurs when a test uses the wrong type of assertion (or a poorly chosen one), which makes the failure message unclear and harder to diagnose. 
test-smell-catalog.readthedocs.io

Example:

.. code-block:: javascript

  test("should update record", () => {
    const record = repository.update(id, data);
    expect(record).not.toBeNull(); // vague assertion
  });

Refactor:

.. code-block:: javascript

  test("should update record and return updated fields", () => {
    const record = repository.update(id, data);
    expect(record.id).toBe(id);
    expect(record.data).toEqual(data);
  });

.. note::
  Use assertions that reflect exactly the expected outcome, not generic ones that hide what failed. 