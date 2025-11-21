Flexible Test
===============
This type of test smell occurs when the test code verifies different functionality depending on when or where it is run — making the test behavior context-sensitive and fragile. 


Example:

.. code-block:: javascript

  test("should behave correctly", () => {
    if (process.env.ENV === "prod") {
    expect(service.run()).toBe("PROD");
  } else {
    expect(service.run()).toBe("DEV");
    }
  });

Refactor:

.. code-block:: javascript

  describe("service.run()", () => {
    test("in production environment", () => {
      simulateEnvironment("prod");
      expect(service.run()).toBe("PROD");
    });

    test("in development environment", () => {
      simulateEnvironment("dev");
      expect(service.run()).toBe("DEV");
    });
  });

.. note::
  Make each test deterministic and independent of external context or environment.