Comments Only Test
========================
This test smell occurs when a test or test case is completely commented out, rendering it inactive. This can negatively impact test execution and harm code readability, making it harder to understand and maintain the test suite. In the example, a fully commented-out test case illustrates this issue.

Example:

.. code-block:: javascript

   // it("should work", () => {
   //   const result = getAge();
   //   expect(result).toBeEqual(10);
   // });

Refactor:

.. code-block:: javascript

   it("should be able to get the age", () => {
   const result = getAge();
   expect(result).toBeEqual(10);
   });

.. note::
   The test case is fully commented and contains unnecessary code. It is recommended to either delete this part or uncomment it.