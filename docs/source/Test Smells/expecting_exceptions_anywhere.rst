Expecting Exceptions Anywhere
=============================
This test smell occurs when tests expect exceptions but do not clearly track the exact step or invocation that should produce the exception, causing ambiguity about what really caused the failure/pass. 



.. note::
  Make sure to pinpoint the invocation expected to fail and assert it explicitly to avoid ambiguous test logic.