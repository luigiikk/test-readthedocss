Time Sensitive Test
====================
This type of test smell occurs when tests only pass depending on the time of day or temporal context in which they are executed. 


Example:

.. code-block:: javascript

  test("should greet good morning", () => {
    const hour = new Date().getHours();
    if (hour < 12) {
      expect(greetUser()).toBe("Good morning");
    } else {
      expect(greetUser()).toBe("Hello");
    }
  });

Refactor:

.. code-block:: javascript

  test("should greet based on provided time – morning", () => {
    const mockTime = new Date("2025-11-25T08:00:00Z");
    expect(greetUser(mockTime)).toBe("Good morning");
  });

  test("should greet based on provided time – afternoon", () => {
    const mockTime = new Date("2025-11-25T15:00:00Z");
    expect(greetUser(mockTime)).toBe("Hello");
  });

.. note::
  Remove dependencies on actual clock/time; make tests deterministic and independent of when they run.