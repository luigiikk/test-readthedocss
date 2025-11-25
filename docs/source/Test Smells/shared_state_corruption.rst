Shared-State Corruption
========================
This test smell occurs when tests share in-memory state (such as static variables or global collections) without properly resetting it, causing one test’s state to corrupt another’s. 


.. note::
  Avoid sharing mutable state across tests. Each test should run with a clean state.