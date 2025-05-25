Only Test
========================
This type of test smell occurs when properties like it.only or describe.only are present in test cases or test suites, which prevents the execution of other tests in the test file.
Example:

.. code-block:: javascript

  describe.only("my beverage", () => {
  test("is delicious", () => {
  expect(myBeverage.delicious).toBeTruthy();
  });

  test("is not sour", () => {
  expect(myBeverage.sour).toBeFalsy();
  });
  });

  describe("my other beverage", () => {
  // ... will be skipped
  expect(myBeverage.sweet).toBeFalsy();
  });

Refactor:

.. code-block:: javascript

  describe("my beverage", () => {
  test("is delicious", () => {
  expect(myBeverage.delicious).toBeTruthy();
  });

  test("is not sour", () => {
  expect(myBeverage.sour).toBeFalsy();
  });
  });

  describe("my other beverage", () => {
  expect(myBeverage.sweet).toBeFalsy();
  });

.. note::
  The use of .only restricts the execution of the test file to a single test or block. It is recommended to remove .only to ensure the complete execution of the test suite.