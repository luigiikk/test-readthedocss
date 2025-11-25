The Painful Clean-Up
========================
This smell occurs when each test requires heavy resource setup or cleanup (e.g., database build, filesystem prep) because test separation is weak or test size is large, causing long runtimes and maintenance burdens. 

Example:

.. code-block:: javascript

  beforeEach(async () => {
    await db.buildLargeSchema();
    await db.loadMillionsOfRows();
  });

  afterEach(async () => {
    await db.dropSchema();
  });

  test("complex workflow", async () => {
    expect(await service.process()).toBe(true);
  });

Refactor:

.. code-block:: javascript

  beforeAll(async () => {
    await db.buildMinimalSchema();
  });

  beforeEach(() => {
    db.clearTestRows();
  });

  test("small scenario", async () => {
    expect(await service.processSmallSet()).toBe(true);
  });

  afterAll(async () => {
    await db.dropSchema();
  });

.. note::
  Minimise heavy resource operations per test. Use shared fixtures sparingly and keep test boundaries clear to reduce clean-up burdens.