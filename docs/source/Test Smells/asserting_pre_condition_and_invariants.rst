Asserting Pre-Condition And Invariants
=========================================
This test smell occurs when the test uses the same API or mechanism to assert both pre-conditions (setup validation), invariants and expected outcomes—meaning the test is mixing concerns and potentially masking which behaviour is under verification. 


.. note::
  Separate testing of pre-conditions, invariants and main behaviour into distinct tests or clear sections. Don’t use the same style of assertion for all.