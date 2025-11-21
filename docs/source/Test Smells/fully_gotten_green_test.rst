Fully Rotten Green Test
========================
This test smell occurs when a test passes (is green) but either contains assertions that are never executed or is otherwise misleadingly indicating success when nothing meaningful was verified. 


Example:

.. code-block:: javascript

  test("should calculate total", () => {
    const result = service.calculate();
    // missing assertion on result, but test passes anyway
  });

Refactor:

.. code-block:: javascript

  test("should calculate total", () => {
    const result = service.calculate();
    expect(result).toBe(100); // actual meaningful check
  });

.. note::
  A passing test that doesn’t assert what it claims gives false confidence.