Curdled Test Fixtures
======================
This smell occurs where there’s an inappropriate union of tests in the same fixture (test class or module), or conversely splitting into multiple fixtures when one would suffice — leading to confusing, poorly organised fixtures. 



.. note::
  Organise fixtures by coherent responsibility and avoid mixing unrelated test concerns in the same fixture.