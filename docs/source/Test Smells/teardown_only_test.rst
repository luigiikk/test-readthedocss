Teardown Only Test
===================
This test smell occurs when a test-suite defines only teardown logic (cleanup) with no actual test logic or assertions, effectively having no meaningful test execution phase. 



.. note::
  Every test suite should include meaningful assertions and behaviour verification — having only teardown logic gives a false green status and no real value.