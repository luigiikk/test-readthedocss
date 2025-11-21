Invasion of Privacy
====================
This test smell occurs when a test is written directly against a method intended to be a private implementation detail of the subject under test, thereby coupling the test to internal rather than observable behaviour. 

Example:

.. code-block:: javascript

  test("should use internal calculation", () => {
    expect(obj._privateCalculate(5)).toBe(25);
  });

Refactor:

.. code-block:: javascript

  test("should calculate result via public API", () => {
    expect(obj.calculate(5)).toBe(25);
  });

.. note::
  Tests should drive the public interface and behaviours of the subject, not its internal private functions.