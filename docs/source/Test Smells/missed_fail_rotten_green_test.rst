Missed Fail Rotten Green Test
=================================
This type of test smell occurs when tests include an assertion primitive intended to force a failure (e.g., assertTrue(false) or fail()) but which is never reached or executed properly, hiding that the test is effectively not validating anything. 


.. note::
  Tests that rely on unreachable fail() calls or similar constructs may pass silently and give false confidence.