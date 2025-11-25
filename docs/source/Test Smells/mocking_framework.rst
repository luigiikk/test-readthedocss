Mocking a Mocking Framework
============================
This test smell occurs when a mock is used to mock the mocking framework’s own mock, increasing complexity and reducing clarity.


.. note::
  Avoid layering mocks on top of mocks of the testing/mocking infrastructure—it indicates the test is overly entangled with its own tooling.