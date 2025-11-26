Exception Catching Throwing
==============================
This test smell occurs when a test method is explicitly dependent on the production method throwing an exception—i.e., the test’s pass/fail outcome depends on catching or expecting that exception rather than verifying expected behaviour. 



.. note::
  Use the test framework’s built-in exception‐assertion features rather than manual try/catch. It improves clarity and avoids hiding unintended exceptions.