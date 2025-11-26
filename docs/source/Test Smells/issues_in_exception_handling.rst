Issues In Exception Handling
==============================
This test smell occurs when a test case succeeds even when an exception is thrown (but the test ignores it) or mis-handles exception expectations, thus hid­ing failures or masking real problems. 


.. note::
  Avoid catching and ignoring exceptions in tests without explicit verification—doing so can mask defects and give a false sense of safety.