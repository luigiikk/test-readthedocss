Premature Assertions
=====================

This test smell occurs when assertions are intermixed with the setup of data and objects in a test, trying to verify that the setup was successful, resulting in a confusing structure like: Arrange-Assert-Act-Assert. 

.. note::
  Separate setup (Arrange), action (Act), and verification (Assert) clearly — avoid intermediate assertions during setup.