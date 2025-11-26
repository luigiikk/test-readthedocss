Noisy Logging
================
This type of test smell occurs when the test logs the state of the fixtures or internal details (console logs, verbose debug output) rather than focusing on clear assertions.
Example:

.. code-block:: javascript

  test("should process data", () => {
    console.log("Setup fixture: ", fixture);
    console.log("Calling subject.process()");
    const result = subject.process(fixture);
    console.log("Result: ", result);
    expect(result).toBe(true);
  });

Refactor:

.. code-block:: javascript

  test("should process data successfully", () => {
    const result = subject.process(fixture);
    expect(result).toBe(true);
  });

.. note::
  Remove extraneous logging from tests. Logs may clutter output, hide failures, and obscure intent.