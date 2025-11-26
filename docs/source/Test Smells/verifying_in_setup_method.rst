Verifying In Setup Method
==========================
This test smell occurs when an assertion is placed inside the setup (e.g., setUp() or fixture initialization) method instead of the test method itself—blurring the line between setup and verification, and making tests harder to read and maintain. 


.. note::
  Keep setup methods limited to arranging state. Move assertions into test methods so verification happens clearly and explicitly.