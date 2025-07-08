Half a Helper Method
========================
This type of test smell occurs when a helper method is created to simplify or reuse logic in tests, but it only performs part of the task. As a result, tests still require additional setup or logic outside the helper, defeating its purpose and reducing clarity.

Example:


Refactor:

.. note::
  Ensure helper methods encapsulate complete, meaningful actions to make tests more concise and expressive. Avoid forcing each test to manually finish what the helper started.