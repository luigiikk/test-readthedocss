The First and Last Rites
=========================

This test smell occurs when repetitive setup and teardown logic is added directly inside each test case. Instead of using proper setup/teardown mechanisms provided by the testing framework, developers manually add the same initialization and cleanup code at the beginning and end of multiple tests. This makes tests harder to maintain and increases code duplication.

Example:

.. code-block:: javascript

  test("Test 1", () => {
  const service = new Service();
  service.connect();

  expect(service.isAvailable()).toBe(true);

  service.disconnect();


  });

  test("Test 2", () => {
  const service = new Service();
  service.connect();

  expect(service.getData()).toBeDefined();

  service.disconnect();


  });

  test("Test 3", () => {
  const service = new Service();
  service.connect();

  expect(service.hasPermission()).toBe(true);

  service.disconnect();


  });


Refactor:

.. code-block:: javascript

  let service;

  beforeEach(() => {
  service = new Service();
  service.connect();
  });

  afterEach(() => {
  service.disconnect();
  });

  test("Test 1", () => {
  expect(service.isAvailable()).toBe(true);
  });

  test("Test 2", () => {
  expect(service.getData()).toBeDefined();
  });

  test("Test 3", () => {
  expect(service.hasPermission()).toBe(true);
  });

.. note::
  Centralizing setup and teardown improves maintainability, reduces duplication, and enhances readability of tests.