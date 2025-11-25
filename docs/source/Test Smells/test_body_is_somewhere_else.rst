Test Body Is Somewhere Else
=============================
This smell occurs when the test method simply calls another method and contains no meaningful logic itself — so the actual body of the test is hidden elsewhere. 

Example:

.. note::
  Keep the test logic directly inside the test method — don’t abstract it away so far that reading the test becomes difficult.