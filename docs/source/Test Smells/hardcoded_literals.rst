Hardcoded Literals
=====================
This test smell occurs when numeric literal values are directly inserted into tests without proper explanation, especially when they represent system-specific or configurable limits.

Example:

.. code-block:: javascript

  test("Sync tasks should be less than threshold", () => {
    expect(countSyncTasks()).toBeLessThan(5);
  });

Refactor:

.. code-block:: javascript

  const MAX_SYNC_TASKS = 5;

  test("Sync tasks should be less than threshold", () => {
    expect(countSyncTasks()).toBeLessThan(MAX_SYNC_TASKS);
  });

.. note::
  Named constants explain meaning and reduce magic numbers.