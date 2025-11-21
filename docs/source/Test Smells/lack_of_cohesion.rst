Lack of Cohesion of Test Cases
===============================
Occurs when test cases in the same suite do not validate related behaviors.

Example:

.. code-block:: javascript

  describe("Utils", () => {
    test("calculate tax", () => { ... });
    test("login user", () => { ... });
  });

Refactor:

.. code-block:: javascript

  describe("Tax Utils", () => {
    test("calculate tax", () => { ... });
  });

  describe("Auth Utils", () => {
    test("login user", () => { ... });
  });

.. note::
  Group tests logically by responsibility.