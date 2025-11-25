Hidden Test Call
==================
This test smell occurs when tests call other tests, meaning one test’s logic is hidden by invoking another test instead of being self-contained. 


.. note::
  Tests should be independent and self-sufficient — avoid redirecting control flow via other tests.