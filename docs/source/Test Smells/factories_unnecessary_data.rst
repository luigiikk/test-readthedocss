Factories That Contain Unnecessary Data
===========================================
This smell occurs when factories (or fixture builders) define more data than necessary for the model or test to function, thus adding overhead and complexity. 


.. note::
  Build only necessary data in factories; avoid overpopulating fixture objects when the test doesn’t need them.