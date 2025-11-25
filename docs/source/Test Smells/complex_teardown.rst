Complex Teardown
=================
This test smell occurs when the fixture teardown is too complex, involving many steps, shared state cleanup, or logic that may affect other tests and reduce test isolation. 


Example:

.. code-block:: javascript

  afterEach(() => {
    removeFiles();
    flushCache();
    disconnectDatabase();
    resetNetworkMocks();
  });

  test("should do something", () => {
    expect(subject.doWork()).toBe(true);
  });

Refactor:

.. code-block:: javascript

  afterEach(() => {
    // Tear-down is limited to exactly what this test set introduced
    cleanupSubjectResources();
  });

  test("should do something", () => {
    expect(subject.doWork()).toBe(true);
  });

.. note::
  Teardown logic should be simple and clearly scoped to what the test created, to avoid side-effects and brittle tests.