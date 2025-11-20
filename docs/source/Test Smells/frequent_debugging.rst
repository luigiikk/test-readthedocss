Frequent Debugging
==================
This smell occurs when ambiguous test outputs force developers to manually debug causes of failures, often due to poor assertions or unclear intent.

Example:

.. code-block:: javascript

  test("Runs workflow", () => {
    expect(run()).toBeTruthy(); // no clear state validated
  });

Refactor:

.. code-block::javascript

  test("Workflow returns success code", () => {
    expect(run().status).toBe("SUCCESS");
  });

.. note::
  Improve assertion quality to reduce guesswork when diagnosing test failures.