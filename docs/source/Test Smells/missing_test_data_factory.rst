Missing Test Data Factory
===================
This type of test smell occurs when each test creates example data in its own way, instead of using a shared test data factory. This leads to duplication, inconsistencies, and makes it harder to update or manage test data across the test suite.

Example:


.. note::
  Use a test data factory or builder to centralize and standardize the creation of test data. This improves maintainability, reduces duplication, and allows you to update test data generation in a single place.

