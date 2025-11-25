Stop in Function
==================
This smell occurs when a test (or setup/teardown) includes a stop statement (e.g., return, process.exit(), throw) which interferes with cleanup or lifecycle logic of the test framework. 


Example:

.. code-block:: javascript

  afterEach(() => {
    if (condition) return; // skip cleanup
    cleanup();
  });

Refactor:

.. code-block:: javascript

  afterEach(() => {
    assumeFalse(condition);
    cleanup();
  });

.. note::
  Avoid unexpected early exits in test lifecycle functions that can prevent proper teardown and lead to flakiness or resource leaks.