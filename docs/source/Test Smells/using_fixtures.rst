Using Fixtures
===============
This type of test smell occurs when a test uses large shared fixtures to prepare and reuse test data, often leading to hidden dependencies, excessive setup, and brittle tests. 


.. note::
  Use fixtures sparingly, prefer explicit creation of necessary data per test or minimal shared setup so each test is clear in what data it depends on.