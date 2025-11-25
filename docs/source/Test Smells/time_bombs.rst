Time Bombs
============
This test smell occurs when tests are sensitive to time-related changes (hours, days, weeks, months) and thus might fail intermittently when crossing such boundaries (e.g., end of month/year, daylight saving changes). 

Example:

.. code-block:: javascript

  test("should handle end-of-year rollover", async () => {
    await subject.process(new Date("2022-12-31T23:59:59Z"));
    expect(subject.result).toBe("…"); // may fail when year changes
  });

Refactor:

.. code-block:: javascript

  test("should handle rollover across boundary", async () => {
    const nearBoundary = advanceTimeToYearEnd();
    await subject.process(nearBoundary);
    expect(subject.result).toBe("…");
  });

.. note::
  Time-sensitive tests should explicitly account for boundaries or be decoupled from system clock so they don’t randomly fail.