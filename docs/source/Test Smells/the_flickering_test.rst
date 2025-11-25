The Flickering Test
======================
This test smell occurs when a test occasionally fails (is flaky), typically due to race conditions or non-deterministic behaviour. 

Example:

.. code-block:: javascript

  test("should load async data", async () => {
    await subject.load();
    expect(subject.data).toBeDefined(); // occasionally fails due to timing
  });

Refactor:

.. code-block:: javascript

  test("should load async data reliably", async () => {
    await subject.load();
    await waitForCondition(() => subject.data != null);
    expect(subject.data).toBeDefined();
  });

.. note::
  Flaky tests are harmful — ensure determinism or proper synchronization to avoid intermittent failures.