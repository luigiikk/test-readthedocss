Test Maverick
===============
This test smell occurs when a test method in the test class is independent of the setup defined in the setUp (or fixture) method. The setup runs but the test doesn’t use it, causing wasted setup and confusion. 

.. note::
  Ensure test methods either use the common setup or belong in a separate fixture/class where they use appropriate setup.