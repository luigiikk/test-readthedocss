Over Exertion Assertion
=========================
This test smell occurs when the implementation of the assertion is heavy (lots of logic) inside the test body rather than using clear assertion libraries or helpers, making the test harder to read and maintain. 


.. note::
  Keep assertion logic simple: calculate expected values in setup or helper, and use proper assertion methods to enhance clarity.