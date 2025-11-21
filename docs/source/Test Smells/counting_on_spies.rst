Counting On Spies
====================
This smell occurs when a spy is injected to observe internal interactions rather than validating the final behavior of the system under test.

Example:

.. code-block:: javascript

  const spy = jest.spyOn(api, "send");

  test("should send data", () => {
    service.process();
    expect(spy).toHaveBeenCalledTimes(1);
  });

Refactor:

.. code-block:: javascript

  test("should return processed result", () => {
    const result = service.process();
    expect(result).toBe("SUCCESS");
  });

.. note::
  Focus tests on observable behavior, not on how dependencies are called internally.