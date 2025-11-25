Missed Skip Rotten Green Test
===============================
This smell occurs when test methods contain guards or conditions to skip part of their execution early under certain conditions (e.g., environment, flag), but still report pass (green) even though some assertions weren’t executed. 


.. note::
  Avoid skipping logic inside tests fluidly — use proper test framework skip/assume mechanisms so assertions always execute when expected.