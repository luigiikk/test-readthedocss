Empty Shared-Fixture
=====================
This test smell occurs when a test suite or fixture defines shared setup/teardown (or shared variables) but the body is essentially empty—there are no meaningful tests or the fixture isn’t used. 



.. note::
  A fixture should support actual tests; having a shared fixture with no test usage wastes complexity and confuses maintainability.